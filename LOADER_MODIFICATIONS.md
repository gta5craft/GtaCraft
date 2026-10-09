# Separate GPL loader: provenance and modifications

Notice dated **9 October 2026**. The derivative source reflects the existing local GtaCraft development through the 7 October wallfix snapshot; this notice is not a new runtime change.

Upstream: [Chiheb-Bacha/RageOpenV](https://github.com/Chiheb-Bacha/RageOpenV), based on martonp96's ClosedIV, pinned at `f742117a5e8ccc359bf3b4644c6bce7dad77cc7a`. Included MinHook source is pinned at `4a455528f61b5a375b1f9d44e7d296d47f18bb18`.

The distinct GtaCraft derivative has a minimal Legacy-only entry point, different ASI/config/log names, disabled console, selected file-read/encryption hooks, signature preflight and address validation, thread-local encryption restoration and failure rollback. It excludes upstream Enhanced and virtual-device paths from its target. The patch and complete relevant source are supplied under `source/tools/collision_assets/loader/` and `source/_asset_tools/RageOpenV/`, with dependency notices. GPL-3.0 remains applicable; no MIT relicensing is claimed.

No prebuilt `GtaCraftRpfLoader.asi` is distributed. The upstream README requests no redistribution of built binaries. A user's independently built file is not automatically equivalent to the development build; the setup can pin a user-reviewed hash, and actual archive loading still requires validation.

## Rebuilding from the source snapshot

The ZIP excludes Git metadata. The supplied `build_loader.py` checks pinned Git revisions, so it cannot run unchanged against a metadata-free vendor snapshot. Use a **fresh build workspace**, obtain the pinned upstream checkout and MinHook submodule from their official repositories, apply the supplied `rageopenv-minimal.patch`, retain the corresponding GtaCraft loader sources alongside it, and follow their CMake/SDK instructions. Do not replace the archive's source without keeping the supplied modifications/notices.

From a copied `source/` tree in the fresh workspace, preserve its existing vendor snapshot separately, then prepare `_asset_tools/RageOpenV`:

```powershell
git clone https://github.com/Chiheb-Bacha/RageOpenV.git _asset_tools/RageOpenV
git -C _asset_tools/RageOpenV checkout f742117a5e8ccc359bf3b4644c6bce7dad77cc7a
git -C _asset_tools/RageOpenV submodule update --init --recursive
git -C _asset_tools/RageOpenV/src/vendor/minhook checkout 4a455528f61b5a375b1f9d44e7d296d47f18bb18
```

Apply the patch with its **absolute path** from `tools/collision_assets/loader/rageopenv-minimal.patch` using `git -C _asset_tools/RageOpenV apply <absolute-patch-path>`. Configure the legitimate ScriptHookV SDK/toolchain as described by the supplied CMake/loader README. Developer helpers contain development-machine tool paths and may need local adjustment; no portable loader build has been certified by preparing this notice.

## Magyar

A külön RageOpenV-származék GPL-3.0 marad; a fenti forrásverziók, patch és teljes megjegyzések megmaradnak. Egyedi loaderbináris nincs a csomagban. A ZIP nem tartalmaz Git-metadatát, ezért a revíziót ellenőrző helperhez új workspace-ben külön pinned checkout/submodule, patch, saját SDK és toolchain kell. A snapshotot tartsd meg, ne írj rá a saját játéktelepítésre. Saját fordítás működése külön ellenőrizendő.
