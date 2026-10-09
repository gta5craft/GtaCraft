# Legal notice and distribution boundaries

Documentation reviewed on **9 October 2026**. This is a project disclosure, not legal advice, publisher permission or a certification of compliance.

## Independent project and original-game requirements

GtaCraft is maintained by **mannin1337 / gta5craft**. Contact: [admin@mannin.hu](mailto:admin@mannin.hu). It is independent of Rockstar Games, Take-Two Interactive, Mojang and Microsoft and has no approval, sponsorship or affiliation from them. See the prominent Minecraft disclaimer in [README.md](README.md).

Users need their own legitimately licensed GTA V Legacy and Minecraft: Java Edition installations and normal accounts/activation. This project does not supply the games, shared accounts, activation keys, authentication bypasses or access to paid content. Use the supported **single-player Story Mode** setup. GTA Online, FiveM and Rockstar's licensed multiplayer services are not targets of this preview.

The preview is made available without a paywall, paid mod access or sales of game content. These statements describe this distribution; they do not add restrictions to rights granted by component source-code licenses or override either game's terms.

## Policy position and remaining uncertainty

Rockstar's [Mod Guidelines](https://www.rockstargames.com/community-resources/mod-guidelines), dated 10 September 2026, impose conditions on modding and retain enforcement rights. The [Story Mode policy page](https://support.rockstargames.com/articles/5NVOAYjcTomO8v6SX2k76k/pc-single-player-mods), updated 15 September 2026, links those guidelines and applicable terms. The guidelines do not constitute a project license or approval.

Rockstar's [copyrighted-material policy](https://support.rockstargames.com/articles/7bNaeoMFTV0iUDGhStTXvz/policy-on-posting-copyrighted-rockstar-games-material) includes unauthorized mod/port promotion and combinations of unrelated intellectual property among potential takedown categories. **Our inference is that this GTA/Minecraft crossover has a material public-release and promotion risk.** Runtime use of separately purchased games and exclusion of copied assets do not establish that this combination is authorized. This project does not claim Rockstar compliance or a safe harbor.

Minecraft's [EULA](https://www.minecraft.net/en-us/eula) distinguishes independently authored mods from redistribution of the game or substantial game content. Its [Usage Guidelines](https://www.minecraft.net/en-us/usage-guidelines) also govern names, branding and presentation. Both game's terms and applicable law remain separate from this repository's code licenses. Neither attribution nor a disclaimer creates missing permissions.

Policies can change. There is no guarantee that rights holders will tolerate this project, that it will remain hosted, or that prompt removal would end every possible claim. The presence of other similar mods does not establish permission for this one. No permission from a rights holder has been obtained or represented by this documentation.

## What is distributed

- Original/adapted mod code, its matched ASI/Fabric binaries, configuration templates, setup scripts, notices and corresponding source.
- The unchanged pinned Fabric API under its retained license, clean Prism metadata and mod-only import archive. Minecraft client/server software, launcher accounts and login data are absent.
- An authored collider DLC: generated box meshes, collision metadata, two authored XML files and simple white textures in unencrypted archives. Shape dimensions use Minecraft 26.3 collision-shape fixtures. It contains no copied Rockstar meshes, texture atlases, shader executable or archive keys identified in the inspected payload.
- The separate GPL archive-loader derivative as source, with its dependencies/notices and marked modifications. **No prebuilt custom loader binary** is supplied; the pinned upstream README requests that built binaries not be redistributed.
- Historical, unedited gameplay screenshots for illustration. Their game content remains owned by its respective rights holders; their inclusion is not a relicensing of that content.

Excluded: original games or patched game clients, Rockstar archives such as `update.rpf`, extracted game art/audio/fonts/models, passwords/tokens/keys, accounts, saves, private runtime logs, CodeWalker tool binaries/source, proprietary ScriptHookV SDK/import library/runtime DLLs, ASI loader DLLs, Prism executable, Java and Microsoft runtime installers. Users obtain external prerequisites from their authors and prepare modified **mods** archives locally from their own installation.

The collider generator uses separately obtained CodeWalker as a build tool. That project's educational source notice is not represented as a blanket permissive tool license. Its code/binaries/keys are not bundled. The reviewed collider inventory was generated from primitives; this scoped provenance finding is not publisher clearance for the crossover.

## Source-code licenses and attribution

The root [MIT license](LICENSE) covers original GtaCraft contributions to the extent the contributors can license them. It does not claim ownership of upstream code or game IP. SkyCraft's MIT notice, MinHook/HDE notices, Fabric API and Gradle notices remain attached to their components. The distinct RageOpenV-derived loader retains **GPL-3.0** and its corresponding source/notice obligations; the root MIT file does not relicense it. Full inventory: [THIRD_PARTY.md](THIRD_PARTY.md).

Names, trademarks, characters and game content belong to their respective owners. References identify compatibility and credit. No vendor logo is used as the project's own logo. Screenshots and third-party content are excluded from any claim that all repository material is original or MIT-licensed.

LLM development is disclosed in the README. It does not guarantee copyright eligibility, independent originality, correctness, security or clearance; upstream authorship and licensing remain relevant.

## Warranty, safety and rights-holder requests

The software is experimental and supplied as-is under the applicable component licenses. It may crash, lose state or behave unexpectedly. Back up saves and mod configuration, use a dedicated Minecraft instance and keep an untouched GTA installation. No guarantee of compatibility, performance, uninterrupted availability or fitness for any purpose is made. Any limitation applies only to the extent permitted by law and does not waive non-waivable statutory rights.

For a rights concern, contact [admin@mannin.hu](mailto:admin@mannin.hu) with the material/URL and basis of the concern. The maintainer intends to review substantiated requests promptly and remove or correct affected material where appropriate. This is not an admission concerning every file or a promise that removal eliminates all potential liability. No rights-holder message has been sent on the maintainer's behalf as part of this preparation.

## Magyar jogi összefoglaló

A projektgazda **mannin1337 / gta5craft**, közvetlen elérhetőség: **admin@mannin.hu**. A GtaCraft független a Rockstar Games, Take-Two Interactive, Mojang és Microsoft vállalatoktól; nincs engedélyezés, támogatás vagy partnerkapcsolat.

Saját, jogszerűen licencelt GTA V Legacy és Minecraft Java szükséges, normál bejelentkezéssel. A cél a GTA Story Mode; Online, FiveM és más hivatalos többjátékos szolgáltatás nem cél. A csomag nem tartalmaz játékot, fiókot, aktiválást megkerülő eszközt, másolt `update.rpf`-et, játékassetet, tokent, kulcsot vagy mentést. A kiadásnak nincs fizetős hozzáférése vagy játéktartalom-értékesítése; a forráslicencek által adott jogokat ez nem írja át.

A 2026 szeptemberi Rockstar-szabályok nem adnak automatikus modengedélyt. A jogvédett anyagokra vonatkozó szabály a nem engedélyezett mod/port promócióját és különböző IP-k kombinálását is érinti. **Ebből azt következtetjük, hogy a GTA/Minecraft crossover nyilvános kiadása és bemutatása érdemi kockázatot hordoz.** A külön megvett játék, assetek kihagyása és disclaimer nem bizonyít megfelelést, levétellel szembeni védelmet vagy jogosulti engedélyt. Más modok létezése sem engedély.

A saját kód meglévő MIT licence mellett minden upstream licenc megmarad; a külön GPL-3.0 loader nem kerül MIT alá. A loader binárisa kimarad, teljes külön forrása és megjegyzései szerepelnek. A collider generált egyszerű geometriát/fehér textúrát használ, a méretek Minecraft collision-fixture-ökből származnak. CodeWalker és játékból származó kulcs nem kerül a csomagba. Ez provenance-megállapítás, nem a crossover kiadói jóváhagyása.

A történeti képeken látható játékanyag és védjegyek jogai a jogosultaknál maradnak; a projekt MIT licence ezeket nem licenceli át. Az AI-fejlesztés nem biztosít eredetiséget, hibamentességet vagy jogi védelmet. A kísérleti mod garancia nélkül kerül átadásra, a jog által megengedett keretek között; nem kizárható törvényes jogokat nem von el. Mentsd a világokat/beállításokat.

Jogosulti megkereséseket a projektgazda haladéktalanul áttekint, és indokolt esetben eltávolítja/javítja az érintett anyagot. Az eltávolítás nem garancia minden lehetséges igény megszűnésére. Ez a dokumentum nem jogi tanács vagy jogi megfelelőségi igazolás.
