# Installation with an AI assistant / AI-segített telepítés

This file belongs to a **experimental public preview**, not a certified clean-machine installer. Read `README.md`/`README_HU.md`, `LEGAL.md`, `THIRD_PARTY.md` and the candidate's actual `VERSION.json` first. Both games must be legitimately licensed. GTA Online and Enhanced are outside scope.

## Before using Start.cmd

The intended friendly flow is **Start.cmd → Browse → Install → Play**. The setup UI is only a way to select paths, install the reviewed mod pair and start configured games. It cannot supply game ownership, resolve distribution rights, authorize downloads from mirrors or make a missing native collider work.

Prepare these separately: GTA V Legacy 1.0.3889.0, official ScriptHookV v3889.0/1158.13 with Legacy ASI loader, a dedicated Minecraft 26.3/Fabric Loader 0.19.5/Fabric API 0.161.0+26.3 instance, Java 25 x64, and the required runtime. Use [ScriptHookV](https://www.dev-c.com/gtav/scripthookv/), [Prism](https://prismlauncher.org/download/windows/), [Fabric](https://fabricmc.net/use/installer/), [Minecraft](https://www.minecraft.net/en-us/download) and [Microsoft](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170) sources.

**Native collider prerequisite:** this preview includes the reviewed authored collider DLC but omits the custom loader binary. A new user must separately prepare a compatible collider mount and build the supported local loader from its complete corresponding source. The source's `tools/collision_assets/loader/README.md`, pinned RageOpenV/MinHook revisions and CMake/build instructions describe that local derivative. A renamed binary or an arbitrary official loader version is not evidence of equivalence. CodeWalker is an external, separately licensed build prerequisite; do not distribute it, copied Rockstar archives or keys. Stop with a concrete missing-dependency report if this setup is unavailable. Do not set proof-validation switches to true to bypass it.

## Reviewable installation steps

1. Read the candidate manifest and compare the ASI/JAR file hashes. Protocol 15 requires the exact current pair. Confirm any source-build artifact corresponds to the supplied source. SDK-stub compilation is not a linked game plugin.
2. Identify the Legacy game folder and **one** dedicated Minecraft instance. Ask the owner to identify ambiguous folders. Do not scan or serialize account tokens, launch command lines, browser sessions or unrelated disks to guess the answer.
3. Ask the owner to close and normally save both games. Back up existing plugin/INI/mod JAR and relevant configuration before an authorized replacement; preserve world saves and existing mods. Record destination paths and changed files.
4. Install/verify external prerequisites through their official tools. The user performs Microsoft/Rockstar/platform authentication. No shared account database, password, key or copied game download belongs in a mod package.
5. Prepare/verify the local loader and collider mount using the user's own installed game and reviewed source instructions. Any modified `mods/update/update.rpf` stays local and is derived from that installation. Never overwrite the vanilla archive or install conflicting archive loaders.
6. Run the candidate's reviewed setup UI if present, choose Browse paths, then Install. Manual equivalent: copy `GtaCraft.asi` and reviewed INI beside `GTA5.exe`; put the matching Fabric mod JAR plus Fabric API into the dedicated instance's `mods/`; move the old mod JAR to backup outside that folder. Preserve the remaining configuration and worlds.
7. For local native Own startup, use `start=overworld`, `ownrender=gta`, empty `join=` in `.minecraft/config/skycraft.properties`. Keep the bundled clean defaults unless the owner chooses a change. Avoid copying absolute developer paths or diagnostic settings. `bVehicleStandInProofValidated` is an evidence gate, not a universal installation toggle.
8. Play only after prerequisite/path/pair checks pass and launch is authorized. The manual alternative is Prism for Minecraft and the licensed platform for GTA Story Mode. Do not drive, spawn, teleport, reset worlds or run a diagnostic cycle as part of a quiet installation. The user will test and report bugs manually.
9. Record the installed pair, backups and changes without secrets. On failure, keep logs local, redact sensitive data before sharing, and restore the paired files with games closed. Do not silently downgrade one half or claim an untested mode works.

## Copyable instruction for an assistant

> Help me prepare this GtaCraft preview on my own licensed GTA V Legacy and Minecraft Java installations. First read the English/Hungarian README, LEGAL, THIRD_PARTY, VERSION and file manifest. Identify prerequisites and review the supplied installation code. Report the exact proposed paths, pair hashes and missing collider/loader dependencies before changing anything. Preserve saves/configuration and back up overwritten mod files. I will sign in myself. Do not upload, publish, send messages, expose credentials, bypass proof gates, overwrite vanilla game archives, launch tests, send game input, reset worlds or kill processes. Use Start.cmd/Browse/Install only when the dependencies are actually prepared and I have authorized the listed file changes; use Play only when I authorize launch. Record what changed and what remains unverified. Stop on an unknown game version, unpaired artifacts or missing native physics prerequisite.

## Magyar telepítési út

Ez kísérleti nyilvános előzetes; a setup nem ad játéklicencet, terjesztési engedélyt vagy működő hiányzó collisiont. Előbb saját Legacy/Story Mode, ScriptHookV, külön Minecraft/Fabric instance, Java 25 és szükséges runtime kell. A loader-bináris kihagyása és a külön collider-mount miatt külön előkészített collider mount és megfelelő forrásból épített loader nélkül nincs teljes natív fizikai telepítés.

**Start.cmd → Browse/Tallózás → Install/Telepítés → Play/Játék** csak a ténylegesen elkészült, átnézett setupnál és igazolt függőségekkel használható. Az útvonalat, protokoll-15 ASI/JAR-párt és mentést előbb ellenőrizd. Játékokat normál mentéssel zárj be; a bejelentkezést te végezd. Ne másolj játékadatot, fiókot, kulcsot vagy más `update.rpf` fájlját. Kézi másolásnál ASI/INI a `GTA5.exe` mellé, összetartozó mod JAR és Fabric API az instance `mods/` mappájába; a régi mod JAR külön backupba kerül. Mentések és más modok megmaradnak.

A helyi natív saját világhoz `start=overworld`, `ownrender=gta`, üres `join=`. Az AI ne kapcsoljon bizonyítékkaput önkényesen, ne indítson tesztkört vagy játékműveletet, és ne használjon világresetet hibajavításként. A felhasználó kézzel játszik és konkrét hibát jelez. Visszaállítás bezárt játékokkal, összetartozó párossal történik.

> Segíts ezt a helyi GtaCraft-változatot a saját licencelt GTA V Legacy és Minecraft Java telepítésemen előkészíteni. Olvasd el a README, LEGAL, THIRD_PARTY, VERSION és fájljegyzék tartalmát, valamint a telepítő kódját. Módosítás előtt mutasd meg a konkrét célútvonalakat, pároshasheket és hiányzó collider/loader-függőségeket. Őrizd meg a világokat/beállításokat, mentsd a felülírandó modfájlokat; bejelentkezni én fogok. Ne tölts fel, publikálj, küldj üzenetet vagy játékinputot, ne mutass hitelesítési adatot, ne kerülj meg bizonyítékkaput, ne írj vanilla archívumot, ne futtass tesztciklust, ne resetelj világot és ne lőj le folyamatot. Install csak az előkészített függőségek és a felsorolt másolások engedélyezése után, Play csak külön indítási engedéllyel. Rögzítsd a változásokat és a nyitott működést; ismeretlen játékverziónál, rossz párosnál vagy hiányzó natív fizikai előfeltételnél állj meg.



Current public-preview status: [CURRENT_RELEASE.md](CURRENT_RELEASE.md), [LEGAL.md](LEGAL.md). Loader source-build caveat: [LOADER_MODIFICATIONS.md](LOADER_MODIFICATIONS.md).
