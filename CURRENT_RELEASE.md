# Current preview / Aktuális előzetes

**Publication documentation: 9 October 2026. Gameplay pair: 7 October 2026 wallfix.** Documentation/license corrections do not change the ASI/JAR gameplay bytes.

| Artifact | SHA-256 |
|---|---|
| `gta/GtaCraft.asi` | `d6103f645a11ebec7f5d874403e10e566de1713b34c829bdf9b677495a2ebeed` |
| `minecraft/skycraft-0.1.0-gtacraft.jar` | `3e94aa5da7ca839af4dfa4836e0e980d3cf33382cafd4151dd0201dee53c8d42` |
| Authored collider DLC | `cfea8bb6c315379f058cbd810f7858272ff900f803f06116e8e638b2c6d8fb00` |

Protocol **15**. Menu defaults to English with live Hungarian selection. Both EN/HU distributions contain the combined README, with English first and Hungarian below it. Their gameplay pair is identical.

The README describes the new wall velocity write order, equipment handoff, gun block loot/hostile targeting, parked-car depth probing, Annihilator guns and five-tower End view budget, alongside inherited features. Full native/Java builds are historical evidence for these exact binaries; preparing this release does not rerun gameplay tests.

The final wallfix lacks post-fix retail acceptance. Stable ground-police pursuit failed the most recent natural-terrain observation. The other-machine native Java crash and other regression risks remain open: [KNOWN_ISSUES.md](KNOWN_ISSUES.md).

The nine-October update corrects stale documentation, component notices and public-distribution metadata. The collider inventory was reviewed as authored primitive geometry/white textures, with fixture-derived shape dimensions. Its inclusion does not clear game-IP policy concerns. The custom GPL loader binary is still absent; first-time source build/mount is required.

Prior reports and screenshots in `docs/` and `screenshots/` are historical, scoped evidence. Their counts must not be added together as a universal release test total. The source snapshot comes from the exact wallfix package; original gameplay artifacts are preserved.

## Magyar

**Dokumentáció: 2026. október 9. Játékbeli modpár: október 7-i wallfix.** Az ASI/JAR változatlan. Mindkét ZIP összetartozó 15-ös párt, angol alapmenüt és kapcsolható magyart tartalmaz; a README angol szövege alatt a teljes magyar változat olvasható.

A legújabb faljavítás után nincs tényleges játékbeli visszamérés; a földi rendőrüldözés utolsó természetes terepi megfigyelése sikertelen volt. Másik gép natív Java-crashének oka és további regressziós kockázatok nyitottak. A mostani munka dokumentációt, licenceket és publikációs csomagot készít, nem új gameplay-javítást.

Saját generált collider van a csomagban; külön loaderbináris nincs. Új gépen loaderfordítás és helyi DLC-mount kell. A licencek/asset-proveniencia ellenőrzése nem a crossover kiadói engedélye.
