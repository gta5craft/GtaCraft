# Known issues / Ismert hibák

Status: 0.1.2. The author reports successful destructive car driving in the installed build. This is a limited gameplay observation; other reported limits remain below.

| Area | Current evidence and practical limit |
|---|---|
| Arcade movement | Dense terrain, delayed block acknowledgements or missing collision data can still stop a car. Bedrock, protected and container blocks stay solid. Automatic car ramps and Franklin step-up need broader gameplay coverage. |
| Overworld police | The last natural-terrain observation saw an owned foot officer disappear after two seconds; no patrol car appeared within 29 seconds. Stable ground pursuit is not accepted. Helicopter activity is not a substitute for this test. |
| Driving along walls | Earlier real drives reproduced stops along a long wall. The final position-before-velocity fix passed 9 targeted checks, with 39 continuous-wall and 2 separating-contact checks, but was not retested in the running game. These counts do not prove complete driving correctness. |
| Minecraft native crash | A MultiMC launch reached bridge connection and Overworld opening, then exited with `0xc0000005`. The faulting module/root cause is unknown; the JVM fatal-error report is still needed. Startup Perflib warnings alone do not establish its cause. |
| Explosive weapons | Earlier RMB spontaneous firing/reload and rocket detonation at the player were reported. Ownership/projectile changes are present, but physical aim/reload/respawn behavior lacks full current acceptance. |
| Vehicle entry and persistence | Earlier seating/ejection, death and saved-vehicle startup reports remain regression risks. Script ownership, handoff and visibility changes do not prove every vehicle/menu/world-transition combination safe. |
| Native climbing | The helper requests GTA climbing on eligible full-cube ledges/shores; GTA animation completion, arbitrary shapes and difficult water edges are not guaranteed. |
| Streaming and depth | Finite local collision/rendering coverage, missing or stale terrain, sharp corners, interiors and camera/authority changes can produce incorrect contact or occlusion. |
| Trains and destruction | Known full-cube bedrock now has an independent leading-end sweep and first-face effect. Retail stopping latency, exact wreck appearance, uninterrupted train passage and every explosive/loot interaction remain unverified. |
| End progression | Five towers and a temporary view budget are implemented. Full fight completion, remote crystal/entity delivery and every camera/occlusion case are not accepted. |
| Installation | The custom archive loader must be built separately and the collider DLC mount prepared. The setup is not a clean-machine, dependency-free one-click installer. |
| Other versions/multiplayer | GTA Enhanced/Online/FiveM, other GTA patches, Minecraft versions, arbitrary resource packs/mods and complete multiplayer synchronization are outside this preview's accepted target. |
| Long sessions | A successful build, fixture or screenshot does not establish hours of crash-free play, complete story compatibility or universal terrain navigation. |

## Magyar

- A készítő az új autós rombolást kipróbálta, működőnek jelezte. Ez korlátozott megfigyelés, nem teljes hibamentességi igazolás. Tömör fal/késő blokkfrissítés még megállíthatja az autót; az autós rámpa és gyalogos fellépés további játékbeli próbát igényel.

- Az Overworldben a rendőr eltűnését megfigyeltük, földi járőrautó nem érkezett a 29 másodperces próbában. A stabil földi üldözés nincs igazolva.
- A hosszú falnál megállást tényleges játékpróba reprodukálta. Az utolsó sebességírási javítás célzott ellenőrzései sikeresek, de új játékbeli visszamérés nincs.
- Egy másik gépen a Minecraft világnyitáskor `0xc0000005` hibával összeomlott. A natív hiba oka még ismeretlen; `hs_err_pid*.log` szükséges.
- Korábbi önálló robbanófegyver-lövés, ülés/kidobás, járműmegmaradás, kapaszkodás, loot és respawn utáni viselkedés továbbra is regressziós kockázat.
- A streaming, mélység, vonatfizika és End-végigjátszás minden szélesetére nincs teljes elfogadás.
- Első telepítéskor külön loaderfordítás és collider-mount kell. Eltérő játékverziók, más modok és multiplayer nem igazoltak.

## Reporting / Hibajelentés

Use GitHub Issues for reproducible technical reports, or contact [admin@mannin.hu](mailto:admin@mannin.hu). Include the release, exact versions, scene, vehicle/weapon, reproduction steps and an image/clip. Redact credentials, personal paths and chat before sharing logs. A native Java crash needs the newest `hs_err_pid*.log`; a console exit code alone is insufficient.

Technikai hibához kiadás, verziók, világ/mód, jármű/fegyver, lépések és kép/videó kell. Naplót csak privát adatok kitakarása után küldj. Natív Java-crashhez a legújabb `hs_err_pid*.log` szükséges, a kilépési kód önmagában kevés.
