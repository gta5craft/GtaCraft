# Train impacts and bedrock — 2026-10-05

## Requested behavior and implementation contract

GTA trains should break through Minecraft blocks with a large explosion effect, continuing without damage from that effect. Bedrock is the exception: an exact bedrock contact stops and disables the train with a visible explosion, without damaging Minecraft blocks at that contact.

This extends the existing local two-game bridge. It does not alter GTA tracks or introduce independent position corrections for trains. The earlier trailer-crash exclusion and occupied-car smoke priority remain part of this update.

- Exported material hints distinguish exact bedrock (`6`), other known protected blocks (`7`), and unavailable/unknown information (`0`). Ordinary road vehicles still cannot break the new protected classes.
- A train-specific atomic input pair uses types `26`/`27` under the existing protocol `15`. The end record carries Minecraft player generation, collision epoch and GTA producer PID, in that order. It cannot be treated as a generic weapon shot.
- The Minecraft recipient checks scene, world, origin and producer authority before accepting the pair and again before queued server work. A bounded radius-eight sphere removes loaded non-bedrock blocks, regardless of ordinary vehicle resistance. It uses a cosmetic explosion emitter rather than a Minecraft explosion that damages entities or echoes back to GTA.
- The GTA side validates locomotive and carriage identities and coherent swept contact. Bedrock takes precedence over breakable contacts in the same admitted scan. Unavailable or incomplete evidence produces no custom blast or collision exclusion.
- Successful input-ring admission is not proof that Minecraft removed a block. Native collider release requires a fresh, coherent Minecraft confirmation that the exact cell is now air. GTA world collision and bedrock collision stay enabled.
- Bedrock contact latches cruise speed and immediate train speed to zero, disables driving and turns off the engine, then emits a visible, damage-free train explosion. The ordinary `EXPLODE_VEHICLE` call is avoided because its collateral car explosions could otherwise damage Minecraft terrain. Trains never enter the ordinary car position-rewind module.

## Verification status

Both complete deliverables were freshly built from unchanged source inputs: the native module linked against the real Script Hook V SDK, and the Fabric build executed all 104 JUnit tests successfully. The current focused checks passed 103/103, with zero failures:

| Current check | Result |
| --- | --- |
| Actual native train module: exact shapes, bedrock precedence, carriage identities, scene changes, queue admission and confirmed-air cleanup | 37 passed / 0 failed |
| Actual Java train dispatch and terrain deletion: authority, dimensions, GUI changes, budgets, loaded cells, bedrock and shape updates | 18 passed / 0 failed |
| Trailer/attachment correction and pending native writes | 26 passed / 0 failed |
| Occupied-first smoke scheduling and Java particle dispatch | 22 passed / 0 failed |
| Full native and Java builds | both exit 0, stable source inputs |
| Fresh full Java JUnit run | 104 passed, no skipped tests or failures |

The train fixtures retain their failing pre-fix runs and subsequent successful runs. The complete SDK build caught a missing declaration for the existing collider cleanup function; that interface was declared, the new shadowing warning was removed, and the final native fixture and full build both passed. No existing collision or renderer behavior was redesigned. Independent review found no material blocker within the bounded implementation.

Final ASI SHA-256: `5aaa84df8d3e8091dccf0fdfeadaa7a1437cdc0dc609e2590269ae225991ed66`.

Final Fabric JAR SHA-256: `7566c2f3d4cb27144ecf98ed83bb1ba8637cea5359052585022a507449135bb1`.

The private source-pinned records are under `_test_runtime/train-bedrock-20261005`: `final-native-sdk-interface-1791231210915027600/result.json`, `java-green-final/receipt.json`, the two current crash/smoke receipts, `release/native-build.json`, `release/java-build.json` and `review/independent-review.md`. The release manifest checks these proofs, their source hashes, complete build logs and deliverable hashes before packaging.

These are controlled native/API boundary tests. No new retail gameplay input was sent. The bedrock event requests a stopped, disabled train with a visible, damage-free explosion; it does not assert that GTA marks every carriage dead or derails it. Actual native stopping, physical collision damage during the terrain-confirmation delay, uninterrupted passage and explosion appearance still require retail acceptance. There is no universal bug-free or frame-rate guarantee.

## Bounds and installation

The sampler handles the verified retail freight, freight2 and metrotrain roots, at most two nearby assemblies within 160 metres and 17 bodies per assembly. Longer or ambiguous assemblies are refused. Sweeps are bounded to 64 metres and 15 degrees between observations, with shared frame limits of 8,192 cell visits, 16,384 boxes and 8,192 exported shape records. Unknown or unsupported contacted geometry leaves native collision intact.

Each train can request one blast per 250 ms. The server clears the loaded cells in an eight-block-radius sphere (2,109 candidate cell centres), including resistant non-bedrock blocks and liquids. It does not load missing chunks, produce loot or propagate neighbour-update destruction outside that sphere. At most four batches are accepted per server tick. Exact bedrock contact takes precedence before publishing a terrain request; its Minecraft blocks receive no blast request. Bedrock elsewhere inside an ordinary blast also remains intact.

The train never receives ordinary car position/velocity rewinds or whole-entity collision disabling. A successful ring publication does not disable a contacted collider. Only a newer, coherent same-epoch Minecraft air record can release the exact captured prop, after rechecking both train and prop identities. This protects against recycled handles, changed scenes and stale work.

The new EN/HU archives carry the same newly built ASI/JAR pair and English default menu, with Hungarian selectable live. **Install both together with GTA and Minecraft closed.** Although the protocol number remains 15, an older JAR lacks train events 26/27 and exact bedrock material export. Packaging is separate from local installation and does not alter game files, saves or settings; deployment status is recorded separately. Earlier archives remain unchanged.

## Related checkpoint

[Trailer crash and own-car smoke](CRASH_SMOKE_2026-10-05.md) records the previous native checkpoint and forensic evidence. Its binary hashes identify that checkpoint, not the later combined train build. Older archives remain unchanged.
