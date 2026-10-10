# Package contents / Csomagtartalom

The EN/HU preview archives carry the **same 0.1.2 mod pair**, including arcade destruction, mouse carjump, step assistance and the earlier bedrock train-contact fix. The full English README is followed by its full Hungarian version. Both menus default to English and allow live Hungarian selection.

Included:

- `Start.cmd` and bilingual `SetupLauncher.ps1`, clean setup manifest/configuration and a mod-only Prism import ZIP.
- Paired `GtaCraft.asi` and adapted SkyCraft Fabric mod; unchanged pinned Fabric API with notices.
- Matching generated `gtacraft_colliders/dlc.rpf` and its provenance manifest.
- Corresponding native/Fabric/protocol/tools source; the **separate GPL loader source**, pinned vendor files, patch and modification notice.
- README, detailed setup, AI installation instructions, current release/known issues, contact, legal/third-party notices, retained full license files and SHA-256 manifests.
- Eight historical gameplay screenshots, with captions distinguishing them from latest-build acceptance.

Not included: games/Minecraft client JAR, Rockstar `update.rpf`, copied game art/audio, account data, saves, private logs, keys, ScriptHookV runtime/SDK, `dinput8.dll`, custom loader binary, CodeWalker, Prism, Java or Microsoft runtimes. These remain external/local prerequisites.

**First-time setup requires building the loader and preparing the local mods archive/DLC list.** Start.cmd does not do those steps automatically. Once the prerequisites/paths are configured, Install/Play request the paired update and normal launches.

The repository documentation and downloadable preview/source archive describe the same snapshot. If source is supplied as an archive rather than individual repository files, extract it before following its build instructions; its presence is not a claim that all sources are directly browseable in the web tree.

## Magyar

Mindkét ZIP azonos 0.1.2-es modpárt tartalmaz az autós rombolással, egérugrással, fellépési segéddel, korábbi bedrock–vonat javítással és angol–magyar dokumentációval. Telepítő/indító, mod-only Prism-import, saját collider, teljes kapcsolódó forrás és külön GPL-loaderforrás, licencek, képek és lenyomatok szerepelnek benne.

Játék, `update.rpf`, másolt játékasset, fiók, mentés, token/kulcs, privát log, ScriptHookV, ASI-loader DLL, egyedi loaderbináris, CodeWalker, Prism, Java és runtime nincs mellékelve. Első telepítéshez külön loaderfordítás és saját mods/DLC-beállítás kell. Archivált forrás esetén a buildhez előbb csomagold ki.
