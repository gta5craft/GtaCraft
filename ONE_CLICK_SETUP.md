# GtaCraft – egyszeri beállítás, egygombos telepítés és indítás

2026-10-09 documentation for the 2026-10-07 wallfix pair. A HU és EN csomag kísérleti előzetes, azonos modbinárisokkal és közös angol–magyar leírással. A `Start.cmd` egy Windows-ablakot nyit; az ablak és a GtaCraft menüje **mindkét kiadásban alapból angol**. A játékban élő magyar váltás: **Insert → Status and keys → Menu language → Magyar**; a választás megmarad. A már előkészített rendszerben egy **Install / Telepítés**, később egy **Play / Játék indítása** gomb elég. Új gépen előbb külön be kell állítani az alábbi előfeltételeket.

## Magyar útmutató

1. Használd a saját GTA V **Legacy 1.0.3889.0** telepítésedet, Story Mode-ban, DirectX 11-gyel és kikapcsolt BattlEye-jal. A GTA és a Minecraft szokásos bejelentkezése a saját hivatalos indítójukban történik.
2. A [Script Hook V hivatalos oldaláról](https://www.dev-c.com/gtav/scripthookv/) külön szerezd be a 3889-hez való ScriptHookV.dll-t és dinput8.dll ASI-betöltőt. A csomag ezeket nem tartalmazza. Ez a kiadás a felülvizsgált fájlok pontos SHA-256 értékét kéri; egy másik kiadás vagy megváltozott fájl új ellenőrzést igényel. Egy régi dsound.dll betöltő jelenlétét külön rendezni kell.
3. Telepítsd a Prism Launchert, importáld a mellékelt Prism-példányt, és állítsd be benne a saját Minecraft-fiókodat. A példány Minecraft **26.3**, Fabric Loader **0.19.5**, **64 bites Java 25** és `--enable-native-access=ALL-UNNAMED` Java-argumentum használatára legyen beállítva. A Java 25 tényleges, létező javaw.exe fájlját válaszd ki a Prism beállításaiban; az automatikus Java-letöltés befejezése előfeltétel. Ez a telepítő Java-programot nem futtat és nem tölt le. A [Prism Java-útmutatója](https://prismlauncher.org/wiki/getting-started/installing-java/) ismerteti a Java kiválasztását; a 25-ös követelmény ennek a GtaCraft/Minecraft 26.3 csomagnak a követelménye.
4. Az archívumbetöltőt külön kell fordítani és beállítani. A módosított GPL forrás és a licenc-/szerzői megjegyzések a `source/tools/collision_assets/loader` és `source/_asset_tools/RageOpenV` alatt vannak. A csomag **nem tartalmaz GtaCraftRpfLoader.asi binárist**. A mellékelt forrásból készített x64 fájl neve legyen GtaCraftRpfLoader.asi, és kerüljön a GTA mappájába. A mellékelt loader README külön ismerteti a fordítást és ellenőrzést. Egy saját fordítás eltérő lenyomata külön jóváhagyható az ablakban; ez fájlazonossági jóváhagyás, a saját fordítás játékbeli működését még külön ellenőrizni kell. Egy azonos nevű, másik archívumbetöltő nem helyettesíti automatikusan ezt a módosított változatot.
5. Külön készítsd elő a collider DLC-t. A fájl helye `mods/update/x64/dlcpacks/gtacraft_colliders/dlc.rpf`; a **mods/update/update.rpf** belsejében lévő dlclist.xml tartalmazza a `dlcpacks:/gtacraft_colliders/` bejegyzést. Az eredeti Rockstar-archívumokat hagyd változatlanul. A csomag saját collider-fájlját a Telepítés gomb a fenti külön mods/DLC helyre másolja, mentéssel; a DLC-listát akkor is külön kell beállítani. A telepítő nem szerkeszt RPF-et: az előkészített mods/update/update.rpf pontos lenyomatát a felhasználó jóváhagyásához köti. A bejegyzés meglétét és a tényleges DLC-betöltést nem állítja automatikusan igazoltnak.
6. Csomagold ki a csomagot, majd nyisd meg a **Start.cmd** fájlt. Tallózd be a GTA mappáját, a telepített PrismLauncher.exe-t, a példány `instance.cfg` fájlt tartalmazó mappáját, a Prism adatmappáját és a hivatalos GTA-indítót/parancsikont. Az adatmappa általában az `instances` mappa szülője. A példány kiválasztása ezt felajánlja; eltérő Prism-könyvtárszerkezetnél javítsd a mezőt.
7. GTA-indítónak a GTA mappájában lévő **PlayGTAV.exe / GTAVLauncher.exe**, ezek közvetlen hivatalos parancsikonja vagy a GTA Legacy Steam/Epic `.url` parancsikonja használható. A GTA5.exe közvetlen indítását a program elutasítja. A Steam Legacy azonosítója 271590 a [hivatalos áruházi oldalon](https://store.steampowered.com/app/271590/Grand_Theft_Auto_V_Legacy/).
8. Zárd be mindkét játékot, jelöld az elvégzett kézi előkészítést, majd válaszd az **Ellenőrzés**, utána a **Telepítés** gombot. A tallózott helyeket és a pontosan jóváhagyott fájlokat megjegyzi. Később a **Játék indítása** gomb a hivatalos GTA-indítót és pontosan ezt a Prism-példányt indítja. Az indítási kérés után a játékok saját betöltése, bejelentkezése és a Story Mode kiválasztása következik.

## English guide

The HU/EN archives are experimental preview packages with identical gameplay binaries and combined English/Hungarian documentation. Extract the archive and open **Start.cmd**. Both editions start with an English setup window and game menu; switch the game menu live through **Insert → Status and keys → Menu language → Magyar**. Once the separate prerequisites are prepared, **Install** updates the paired mod files and **Play** starts the legitimate GTA launcher and the selected Prism instance. First-time setup is not fully automatic.

Prepare your own **GTA V Legacy 1.0.3889.0**, Story Mode, DirectX 11 and disabled BattlEye. Obtain the matching ScriptHookV.dll and dinput8.dll separately from the [official Script Hook V site](https://www.dev-c.com/gtav/scripthookv/). This package pins the reviewed dependency hashes and does not distribute these binaries. Resolve an old dsound.dll ASI loader manually.

Install Prism, import the supplied instance and configure your own Minecraft login. The instance must use **Minecraft 26.3, Fabric Loader 0.19.5, 64-bit Java 25** and `--enable-native-access=ALL-UNNAMED`. Complete Java setup in Prism and select an existing Java 25 javaw.exe path. The installer reads the runtime metadata; it never executes or downloads Java. The included matching Fabric API is installed if absent; a different existing Fabric API must be resolved manually.

Build/configure **GtaCraftRpfLoader.asi** separately from the supplied modified GPL loader source and its notices. The package does not ship that loader binary. Keep the `source/tools/collision_assets/loader` and `source/_asset_tools/RageOpenV` layout together. Read the loader README and perform its separate validation. A user-confirmed local build can be pinned by exact path and SHA-256; compatibility of that different build remains unvalidated until a manual in-game test. Stock or unrelated archive loaders are not automatically equivalent.

Configure the collider DLC at **mods/update/x64/dlcpacks/gtacraft_colliders/dlc.rpf**, and add **dlcpacks:/gtacraft_colliders/** to dlclist.xml inside **mods/update/update.rpf**, using your separately configured archive tooling. Preserve Rockstar's original archives. The included authored collider is copied only to its own mods/DLC location with a backup. The installer does not edit archives or inspect their encrypted DLC configuration: you explicitly acknowledge the prepared mods archive, whose exact hash is remembered. Actual DLC mounting still needs manual validation.

Browse to the GTA folder, installed PrismLauncher.exe, imported instance folder, Prism data folder and official GTA launcher/store shortcut. The data folder normally contains `instances`; check it if using a custom InstanceDir. Choose **PlayGTAV.exe / GTAVLauncher.exe** inside the GTA folder, its direct official shortcut, or the GTA Legacy Steam/Epic `.url` shortcut. Raw GTA5.exe is rejected. Close both games, acknowledge the separate preparation and choose **Check setup**, then **Install**. Selections are remembered; **Play** rechecks prerequisites and the installed pair before sending normal launch requests. Account selection, sign-in and game loading remain in the official launchers.

## Megőrzés, visszaállítás / Preservation and recovery

- A mentések, options.txt, a Prism-példány beállításai és a többi mod változatlanok. Csak az `id=skycraft` Fabric-modok régi példányait veszi ki a mods mappából; a fájlnév önmagában nem azonosít modot. Azonos célfájlnevet használó idegen mod esetén megáll.
- A meglévő GtaCraft.ini minden más beállítása és kódolása megmarad. Csak a `[GtaCraft]` szakasz `sMenuLanguage=hu/en` kulcsát frissíti; hiányzó INI-nél a csomag alapbeállításából indul. A később megváltoztatott saját INI-beállítások nem teszik hibássá az ASI/JAR párost.
- Előbb minden fájlt a cél meghajtójára készít elő, és menti a korábbi saját fájlokat. Ezután cseréli az ASI-t, INI-t, JAR-t, szükség esetén a mellékelt Fabric API-t/collidert és a saját telepítési bizonylatát. Hiba esetén a már cserélt saját fájlokat visszaállítja.
- **Két külön meghajtó között a teljes páros nem tehető fizikailag egyszerre atomivá áramkimaradás esetén.** A játékok bezárásának ellenőrzése, az egyenkénti atomi fájlcsere, a napló és a Play előtti pontos hash-ellenőrzés akadályozza meg egy félkész páros elindítását. Függőben maradt vagy hibás visszaállítási naplónál a program megáll.
- A választások és a mentési napló helye `%LOCALAPPDATA%\GtaCraftSetup`; a régi fájlok a `backups/<azonosító>/` alatt maradnak. A `restore-manifest.json` minden korábbi fájlt és annak eredeti célhelyét felsorolja. Megszakadt telepítés után, bezárt játékok mellett, ebből kell a **teljes korábbi állapotot** helyreállítani: az `existed=true` rekordok `.previous` fájljait az eredeti helyükre, az `existed=false` rekordok által valóban létrehozott új fájlokat eltávolítani. Ne csak a `committed` számlálóra hagyatkozz: a rendszer leállhatott egy fájlcsere és a következő naplóírás között. A napló csak a ténylegesen befejezett helyreállítás után jelölhető `rolled_back` állapotúnak. Bizonytalan helyreállításnál kérj segítséget a megőrzött naplóval.
- A loader, ScriptHookV, dinput8 és a mods/update/update.rpf fájl nincs felülírva. A jóváhagyott loader/archívum későbbi változása ismét megállítja az ellenőrzést. A saját helyi loader jóváhagyása a jelenlegi fájlra vonatkozik, nem minden későbbi változatra.
- Ha egy védett GTA-mappa nem írható, a program hibával megáll; nem kér automatikusan rendszergazdai jogosultságot. A mentések megőrzésével külön rendezd a mappa írási jogosultságát.

Saves, options, Prism settings and unrelated mods are preserved. Only old Fabric mods whose real ID is `skycraft` are removed from the active mods folder; originals remain in the backup. Only the GtaCraft INI language key changes. A failed commit rolls back files already replaced. A power loss across different volumes cannot be physically atomic; an interrupted journal blocks Install and Play until the complete original state is restored from its restore manifest. Restore every original operation, not only the recorded committed count, because a crash may occur between a file replacement and a journal update. Mark `rolled_back` only after a verified restoration. Backups and selections live under `%LOCALAPPDATA%\GtaCraftSetup`. The installer does not overwrite dependency binaries or Rockstar archives.

## Csomagolási szerződés / Packaging contract

A csomag gyökerébe kerüljön a `tools/distribution/Start.cmd`, `tools/distribution/SetupLauncher.ps1`, a jelen útmutató **ONE_CLICK_SETUP.md** néven, valamint **SETUP-MANIFEST.json**. A GTA és Minecraft payloadok maradjanak a manifestben megadott relatív helyen. A PowerShell-fájl UTF-8 BOM-os, hogy Windows PowerShell 5.1-ben a magyar szöveg is helyesen jelenjen meg.

Kötelező JSON-mezők:

```json
{
  "schema_version": 1,
  "protocol_version": 15,
  "menu_language": "en",
  "requirements": {
    "gta_file_version": "1.0.3889.0",
    "minecraft_version": "26.3",
    "fabric_loader_version": "0.19.5",
    "java_major": 25,
    "script_hook_sha256": "126be57ca9dca00e471f9de611766009c900aad88f89ae6c2926ec62e5aaeb4f",
    "asi_loader_sha256": "9fd9e02353b7d39fe07b9667f7ea2697229a7f2d0e7d389eb79eb212b1bb181d",
    "archive_loader_path": "GtaCraftRpfLoader.asi",
    "archive_loader_sha256": "ad060b87250de458a8ef05cf5e00e5b05246428ef9a89518fec5f26dd470a4f9",
    "collider_install_path": "mods/update/x64/dlcpacks/gtacraft_colliders/dlc.rpf",
    "collider_sha256": "cfea8bb6c315379f058cbd810f7858272ff900f803f06116e8e638b2c6d8fb00"
  },
  "payloads": {
    "asi": { "path": "gta/GtaCraft.asi", "sha256": "ACTUAL_64_HEX_SHA256" },
    "jar": { "path": "minecraft/skycraft-current.jar", "sha256": "ACTUAL_64_HEX_SHA256" },
    "ini": { "path": "gta/GtaCraft.ini", "sha256": "ACTUAL_64_HEX_SHA256" },
    "fabric_api": { "path": "minecraft/fabric-api-current.jar", "sha256": "ACTUAL_64_HEX_SHA256" }
  }
}
```

Az `ACTUAL_64_HEX_SHA256` helyére a **végleges, ténylegesen csomagolt fájl** SHA-256 értéke szükséges; a példa nem telepíthető manifest. A HU és EN kiadásban is `menu_language` legyen `en`; a magyar játékmenü élőben választható. Opcionális `payloads.collider={"path":"sajat/relativ/dlc.rpf","sha256":"…"}` csak a requirements.collider_sha256 értékével egyező saját DLC-hez adható. Tiltott a csomaggyökéren kívüli út, fájlfolyam vagy link/junction; nem szerepelhet új, a telepítő által nem ismert payload-kulcs. A manifest és a fájlhash egyezése a csomag belső konzisztenciáját ellenőrzi, kiadói digitális aláírást nem helyettesít.

A Java/protocol követelmény a csomag helyi forrás- és buildadataiból származik. A Prismet a dokumentált `--dir <adatmappa> --launch <példánymappa-neve>` parancssori API indítja, fiókválasztási kapcsoló nélkül. [Hivatalos Prism CLI](https://prismlauncher.org/wiki/getting-started/command-line-interface/).

## Ellenőrzés / Validation scope

A `tools/distribution/test_one_click_setup.py` Windows PowerShell 5.1 alatt, külön ideiglenes tesztmappákban futtatja a valódi telepítési függvényeket. A játékfolyamat- és GTA-előfeltétel-lekérdezési határ tesztstub; a fájl-/ZIP-/hash-/INI-/napló-/visszaállítási útvonal és a Prism Minecraft/Java ellenőrzése valódi. A zárolt JAR-próba igazolja, hogy a hiba az ASI és INI tényleges cseréje **után** történik, és mindkettő visszaáll. A PE-próba csak bájtokat olvas; nem tölt be DLL-t. A tallózó callback által használt eredeti mezőgyűjtemény és az automatikus útvonalajánlás elkülönített próbában ellenőrzött.

Ezek a tesztek nem nyitnak WinForms-ablakot, nem indítják a GTA-t, Prismet vagy Java-t, és nem végeznek telepítést a felhasználó játékában. A tényleges ablak vizuális működése, a jogosultságok különböző Windows-telepítéseken, a hivatalos indítók indítási viselkedése és egy friss felhasználó teljes előkészítési folyamata még külön kézi átvételi próbát igényel. A DLC-mount és egy másik helyi loader játékbeli kompatibilitása ebből a fájlpróbából nem állapítható meg.


Current public-preview status: [CURRENT_RELEASE.md](CURRENT_RELEASE.md), [LEGAL.md](LEGAL.md). Loader source-build caveat: [LOADER_MODIFICATIONS.md](LOADER_MODIFICATIONS.md).
