# Building the supplied sources

Use the source/ directory as the repository root. The proprietary ScriptHookV SDK, games, Java, compiler tools and dependency runtimes are obtained separately.

Native: Visual Studio 2022 C++ x64 build tools and CMake. Place your legitimate ScriptHookV SDK inc/ and lib/ directories at asi/sdk/. Run asi/build.bat from this source tree; output is asi/build/Release/GtaCraft.asi. A stub compile is not a game plugin.

Java: use a 64-bit JDK 25. From fabric/ run gradlew.bat build (or ./gradlew build). The normal build runs the included tests and writes build/libs/skycraft-0.1.0-gtacraft.jar. First use needs access to the declared Gradle/Fabric/Minecraft dependency repositories. Those dependency caches and game jars are not shipped. Do not publish Minecraft cache jars. If a restricted environment rejects the normal Gradle cache or temporary test-world directory, configure writable local Gradle/test temporary locations; do not skip failing tests.

Keep the matching protocol-15 native and Java pair together. Test scripts under tools/ are supplied as developer fixtures; some require separately configured MSVC/JDK tools and local paths. The included test receipts describe the build machine's checks, not portable retail certification.

The modified archive loader is separate corresponding GPL source. Keep tools/collision_assets/loader/ alongside _asset_tools/RageOpenV/ and follow the loader README for its pinned dependencies, CMake build and separate validation. Its ASI binary is not in this ZIP.

The original collider generator source requires separately obtained CodeWalker and .NET. No proprietary SDK, CodeWalker, game data or runtime is shipped. Respect each dependency's original notices and LICENSE files.


## Loader snapshot metadata

See [LOADER_MODIFICATIONS.md](LOADER_MODIFICATIONS.md): the helper requires pinned Git metadata, which ZIP snapshots omit. Prepare a separate fresh pinned checkout, apply the supplied patch, and retain the complete GPL source/notices. Build tool paths may need local configuration.
