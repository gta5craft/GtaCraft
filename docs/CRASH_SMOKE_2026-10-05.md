# Own-vehicle smoke and native script crash — 2026-10-05

This is the earlier native checkpoint. The later [combined train/crash/smoke release](TRAIN_BEDROCK_2026-10-05.md) retains these fixes and freshly rebuilds both modules; its new hashes and current check counts supersede this checkpoint for installation.

The observed unsafe trailer correction is excluded, and the occupied car receives its smoke batch before ambient traffic. The checkpoint's full Script Hook V native build passed. **48 focused checks and 70 adjacent collision checks passed**, with zero failures. These are controlled boundary tests, not a claim that every GTA engine crash or visual effect is verified in retail gameplay.

## What caused this report

At 21:09:04 local time, Script Hook V stopped GtaCraft's script thread after an access violation (`0xc0000005`) at `GTA5.exe+0x00eac89c`. Its render thread continued, so subsequent F9 requests could still appear in the log without being serviced by the failed script. The game's zero "last called native" field did not identify the caller.

The installed ASI, matching MAP/PDB, log and dump establish the call chain: `VehicleImpact::Update` → `Sweep` → `Constrain` → `SET_ENTITY_COORDS_NO_OFFSET`. The corrected body was an **ambient, driverless log trailer**, handle 768274, model `trailerlogs` / `2016027501`; it was not the player's taxi or a smoke emission call. The model hash also matches the [primary Cfx vehicle reference](https://docs.fivem.net/docs/game-references/vehicle-references/vehicle-models/).

The trailer had travelled only 0.147 m. Its long, rotated bounding box exceeded the existing 512-cell query budget, causing a `CellLimit` correction without a certified terrain contact. Native coordinates were finite and correctly packed. The captured fault reads through a null engine pointer; the proprietary object's type and the trailer's attachment state cannot be established from this dump.

The frozen evidence is private under `_test_runtime/crash-smoke-20261005/evidence`. Original dump SHA-256: `d1e5551c8f9b38a4d456be38351d4944f8903bfaefae0fb5f6525989d42c91ae`. Matching old ASI: `24bb36057456f1aaf6e2416f2633c514bbc77e415256f6652a778d0401a05115`. Neither the dump nor game binaries are included in the distribution.

## Vehicle correction

The independent correction module now admits unattached road cars/trucks, bikes, bicycles and quad bikes using the SDK's model predicates. Trailers and attached child vehicles remain under GTA's native assembly physics. The shared eligibility check protects sampling, native constraint writes, pending-break velocity credits and momentum restoration. A rejected sample drops its old motion history, preventing a later detachment from replaying stale towing motion.

Confirmed Minecraft block removal still releases the corresponding collider even if the former vehicle is attached or ineligible; it does not grant a native velocity write. A final check after reading velocity closes the pending-credit attachment gap found during review. Query budgets, real-wall protection, unknown-terrain barriers, teleport flags and the existing long-frame braking fix remain intact.

## Own-car smoke

Previously the sender sampled a rotating list of at most 256 world vehicles every 100 ms, processing no more than 16 nearby vehicles or 64 particle events. The occupied vehicle had no priority. Busy traffic could exhaust an interval before reaching the player's car, and a car omitted from the enumerated list received no events.

The verified occupied car now goes first through the existing geometry and scene checks, even when world enumeration omits it. Ambient duplicates are skipped, traffic rotation continues, and occupancy is checked again before publishing the priority batch. The same 16-vehicle/64-event/100-ms limits apply. Exhaust is produced with the engine running, drift smoke during supported sliding/burnout, and flames while a car is burning, in both rendered worlds. Particle density, rear positions, billboards, depth and HUD rendering were not increased or redesigned; a single exhaust outlet retains its 10-event/second cadence.

## Verification and build

| Current check | Result |
| --- | --- |
| Recorded trailer, attached body, pending credits, supported road vehicles | 26 passed / 0 failed |
| Occupied-first smoke scheduling and Java particle dispatch | 22 passed / 0 failed |
| Actual-source long-frame wall/reverse/unknown-terrain controls | 25 passed / 0 failed |
| Actual-source float coordinate/history round trips | 45 passed / 0 failed |
| Full native build linked against the real Script Hook V SDK | exit 0, unchanged source fingerprints |

The original trailer/attachment failures were observed before the admission fix. The first new test run also exposed one fixture reset error in a positive control; that was corrected separately and retained in the evidence. The later pending-read callback defect was reproduced as 25 passing / 1 failing check, then passed all 26 after the final recheck. Smoke had five failing priority controls before the fix and all 22 checks passed afterward. Independent reviews found no remaining material blocker in these narrow changes.

Final native ASI SHA-256: `437aa17dfd4335efc1fbb3403cfb4d4578c1d27e0f4c5dbeb42c2cb6e3437a5f`.

Unchanged matching Fabric JAR SHA-256: `5ebfdbd672c7eaf0e0045625056aa990a50d8ed56021c6682c52068110fd5dc3`. All 150 Java build inputs match the prior full build. Its 104 JUnit results are **carried historical evidence**, not a new Java run. Protocol remains 15. Earlier reports and archives remain historical checkpoints.

## Installation and remaining limits

This native-only checkpoint was built and retained privately, without emitting a separate crash-only ZIP. The subsequent train EN/HU packages contain the newly built mod pair, README, source and setup launcher; both start with an English menu and retain the Hungarian toggle. **The combined train update requires both games closed and both ASI and Fabric JAR replaced together.** The unchanged-JAR native-only option described during the checkpoint investigation does not apply to that later update. Neither procedure should touch saves or user settings.

No new retail pursuit, driving or rendered exhaust trial was completed for this patch. The Windows Computer Use helper had already failed its prescribed recovery; this investigation did not send gameplay input, launch or move a game window. The tests reproduce the mod's unsafe native-call path with controlled native boundaries, rather than reproducing a proprietary engine access violation. The exact engine null object's cause remains unknown. Trailer assemblies do not receive independent software correction, and ordinary very large queries retain conservative budget stops. See the separate local installation receipt for any performed deployment.
