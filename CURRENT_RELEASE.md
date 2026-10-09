# GtaCraft 0.1.1 / Aktuális kiadás

Bedrock now has a separate, bounded sweep of each moving train body. A known, exact full-cube hit can stop the whole assembly before the next frame's predicted penetration, without waiting for unrelated unloaded sections. The effect is placed on the earliest contacted face. Ordinary block destruction still requires its complete collision proof.

Validation: **46 controlled native checks passed** and the full ScriptHookV SDK build succeeded. The tests compile the actual controller with controlled game/cache boundaries; no games were started. Retail braking latency and wreck appearance have not been retested.

| Payload | SHA-256 |
|---|---|
| `gta/GtaCraft.asi` | `265f6fff17da206642cb9c9051aac034a935fe6d5b1bf8a5edaf370327f48df7` |
| `minecraft/skycraft-0.1.0-gtacraft.jar` | `3e94aa5da7ca839af4dfa4836e0e980d3cf33382cafd4151dd0201dee53c8d42` |

Protocol 15. The Minecraft JAR, collider, configuration and dependencies are unchanged. Both EN/HU ZIPs contain identical gameplay files and bilingual documentation; the menu defaults to English with Hungarian selectable.

## Magyar

Az ismert bedrock külön vizsgálatot kapott: az elöl haladó vonatvég következő képkockára számolt érintése megállítja az egész szerelvényt, és az első felületre kerül a robbanáseffekt. Mellékes, betöltetlen területekre nem vár. A többi blokk rombolási ellenőrzése megmaradt.

**46 célzott kódellenőrzés sikeres, a teljes SDK-build elkészült.** Játékot nem indítottunk; a valódi játékbeli fékezési késést és roncs megjelenését még nem mértük újra. A Minecraft JAR és a 15-ös protokoll változatlan.
