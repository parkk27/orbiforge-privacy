# orbiforge-privacy

# OrbitForge — 3D Orbital Mechanics & Procedural Planet Sandbox

**OrbitForge** is an offline Android 3D spaceflight simulator & GPU conformance sandbox built with **Jetpack Compose**, **Filament 1.81.0 (`Vulkan 1.1` & `OpenGL ES`)**, **OpenGL ES 2.0**, **Room SQLite**, and a built-in **Unity 6 C# Companion Studio**.

- **Application ID:** `com.orbitforge.spaceflight` (`minSdk = 24`, `targetSdk = 36` / Android 16, `compileSdk = 37`, 16 KB page-size aligned)

## Key Capabilities
1. **Vehicle Assembly Building (VAB):** Engineer multi-stage rockets with live Tsiolkovsky Delta-V, surface-gravity-adjusted TWR, and stage-by-stage mass analytics.
2. **Multi-Body N-Body 3D Flight:** Velocity-Verlet symplectic gravity across Primary Planet, Mun, and Minmus with live Sphere of Influence (SOI) transfers, Elliptical Orbit Designer, soft lunar/planetary landings (`<= 12 m/s`) + surface re-liftoff, and live GPU/FPS diagnostics.
3. **Procedural Planet Lab:** Seeded 3D Cube-Sphere terrain + 2D equirectangular heightmaps & Whittaker biome classification.
4. **Filament GPU Lab (`Vulkan 1.1` vs. `OpenGL ES`):** Deterministic 5-scene offscreen (`512x512`) PBR conformance benchmark comparing `Engine.Backend.VULKAN` and `Engine.Backend.OPENGL` with dual raw (`0px`) and `1px` neighborhood-tolerant image diffing, visual heatmaps, and live silicon/Vulkan `dEQP` baseline inspection.
5. **Unity 6 C# Studio:** Ready-to-copy `NBodyGravityEngine.cs`, `KeplerOrbitSolver.cs`, `ProceduralPlanetGenerator.cs`, and synced World JSON exports.

## Build & Sign Locally
1. Generate your Google Play Upload Keystore (4096-bit RSA):
   ```bash
   chmod +x scripts/*.sh gradlew
   ./scripts/generate_upload_key.sh
   ```
2. Run unit tests and build the signed Play Store `.aab`:
   ```bash
   ./scripts/build_release_aab.sh
   ```
   Output bundle: `app/build/outputs/bundle/release/app-release.aab`

## Play Store Assets Included
Ready-to-upload exact-dimension assets are pre-generated in `play_store_assets/`:
- `icon_512x512.png` (`512 x 512` 32-bit PNG)
- `feature_graphic_1024x500.png` (`1024 x 500` PNG)
- `screenshot_1_vab.png` through `screenshot_4_unity_studio.png` (`1080 x 1920` 9:16 PNGs)
- Standalone hostable Privacy Policy: `docs/privacy-policy.html`
