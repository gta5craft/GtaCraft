# Credits, licenses and external prerequisites

Inventory updated **9 October 2026** for the 7 October wallfix pair. Full notices accompany the relevant source and appear in `licenses/`. This inventory is not a relicensing of every file under MIT. Game-IP clearance is addressed separately in [LEGAL.md](LEGAL.md).

## Included code and material

| Component | Attribution and scope | License/notice |
|---|---|---|
| GtaCraft original contributions | mannin1337 and GtaCraft contributors; native plugin, adaptations and tools, to the extent contributors can license them | Root [LICENSE](LICENSE), MIT |
| [SkyCraft](https://github.com/chasmlol/SkyCraft) | chasmlol; Fabric fork, shared-memory protocol and bridge/rendering foundation. Legacy SkyCraft/Skyrim names remain in metadata/code. | Full MIT notice: `licenses/SkyCraft-MIT.txt`, `source/protocol/LICENSE-SkyCraft.txt`, Fabric source license and built JAR's `LICENSE_skycraft` |
| [MinHook](https://github.com/TsudaKageyu/minhook) | Tsuda Kageyu; main native hook library, v1.3.4, and pinned dependency in the separate loader | Preserve the **complete** component license file, including HDE32/HDE64 notices: `licenses/GtaCraft-MinHook.txt`, `licenses/MinHook-LICENSE.txt`. The inspected pinned notices have two conditions; do not replace them with a generic three-clause label. |
| HDE32/HDE64 | Vyacheslav Patkov; disassembler portions included in MinHook | Their full copyright, conditions and disclaimer are in the retained MinHook files. |
| [RageOpenV](https://github.com/Chiheb-Bacha/RageOpenV), based on ClosedIV | Chiheb-Bacha and martonp96; **distinct** minimal Legacy loader derivative, upstream commit `f742117a5e8ccc359bf3b4644c6bce7dad77cc7a`, MinHook commit `4a455528f61b5a375b1f9d44e7d296d47f18bb18` | GPL-3.0 source: `source/_asset_tools/RageOpenV/`, `source/tools/collision_assets/loader/`, `licenses/RageOpenV-GPL-3.0.txt`. See dated [loader modification notice](LOADER_MODIFICATIONS.md). Upstream requests no built-binary redistribution, so the custom ASI is omitted. |
| [inifile-cpp / inicpp](https://github.com/Rookfighter/inifile-cpp) | Fabian Meyer, copyright 2015; header retained in the loader's vendor source | Full MIT copyright, permission and disclaimer: `licenses/inicpp-MIT-LICENSE.txt`. The older short attribution file alone is insufficient. |
| [Fabric API](https://github.com/FabricMC/fabric) | FabricMC contributors; pinned unchanged `0.161.0+26.3` runtime JAR and its modules | Retained Apache-2.0 notice: `licenses/Fabric-API-LICENSE.txt`; embedded module notices remain in the supplied JAR. |
| [Gradle wrapper](https://github.com/gradle/gradle) | Gradle contributors; source-build bootstrap files | Retained Apache-2.0 notice: `licenses/Gradle-Wrapper-LICENSE.txt`. Gradle distribution/cache is obtained separately. |
| Authored collider DLC | Generated box meshes, collision metadata, simple white textures and XML. Dimensions derive from Minecraft 26.3 collision-shape fixtures. | Distributed with GtaCraft contribution scope, subject to [the provenance and game-IP boundaries](LEGAL.md). Manifest: `docs/collider-asset-generation-manifest.json`. No copied Rockstar mesh/texture/key was identified in the reviewed unencrypted payload. |

The GPL loader is a separate component; it is not covered by the root MIT license. Its supplied corresponding source includes the marked modifications and pinned vendor dependency files. Build inputs obtained separately remain subject to their authors' terms.

## Development-methodology credit

[universal-modder](https://github.com/rehan-remade/universal-modder), by **Rehan and universal-modder contributors**, was consulted as a development workflow/methodology reference. Its own MIT notice is retained at `licenses/universal-modder-MIT.txt`. This does not claim that its separate WebSocket/ReShade runtime is linked or included in GtaCraft. Do not import an unrelated project's dependencies or relabel its authorship as ours.

GtaCraft-specific development used LLM agents, including Claude and OpenAI Codex, with human direction/playtesting. Upstream authorship remains distinct; see [README](README.md).

## Required downloads, not bundled

- [ScriptHookV and Legacy ASI loader — Alexander Blade](https://www.dev-c.com/gtav/scripthookv/). Runtime DLLs, proprietary SDK/import library and ASI loader DLL are not supplied.
- [Prism Launcher](https://prismlauncher.org/download/windows/) and normal Minecraft authentication. Prism binaries/accounts are not supplied; its own license applies to separately obtained software.
- [Fabric Loader](https://fabricmc.net/) and Minecraft itself, obtained through the configured launcher/authorized sources.
- Java 25 x64, Visual Studio/CMake build tools and, if required, the [Microsoft Visual C++ runtime](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist).
- [CodeWalker](https://github.com/dexyfex/CodeWalker), if regenerating collider assets: a separate build tool with an educational source notice. Its checkout, DLLs, dependencies and derived keys are not bundled or represented as generally MIT-licensed.
- Both original games and their official platform launchers. Their licenses, content and trademarks remain separate.

The source has optional developer references to e4mc; the release does not ship it as an advertised supported multiplayer service. SkyCraft's Skyrim-specific native dependency inventory is not a claim that this GTA ASI links those libraries.

## Magyar

A saját GtaCraft-hozzájárulások a meglévő MIT hatókörében szerepelnek; az upstream jogi megjegyzések teljes egészükben megmaradnak. SkyCraft: chasmlol, MIT. MinHook/HDE: Tsuda Kageyu/Vyacheslav Patkov, a konkrét teljes fájl feltételeivel. A külön RageOpenV/ClosedIV loader forrása GPL-3.0, nem MIT; egyedi binárisa kimarad. Fabian Meyer inicpp-kódjához a teljes 2015-ös MIT-megjegyzés jár. Fabric API és Gradle wrapper saját Apache-megjegyzései megmaradnak.

A collider egyszerű generált geometriát/fehér textúrát tartalmaz; méretei Minecraft collision-fixture-ökre épülnek. A universal-modder módszertani kredit, nem a külön runtime beépítésének állítása. ScriptHookV, Prism, Java, CodeWalker, compiler/runtime, eredeti játékok és fiókok külön beszerzendők. A játék-IP, képek és védjegyek jogait nem adja a projekt MIT licence.
