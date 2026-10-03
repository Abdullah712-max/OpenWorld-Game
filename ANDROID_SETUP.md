# Android build settings (Unity 6 LTS)
Install via Unity Hub: Android Build Support + OpenJDK + Android SDK & NDK.

Project Settings > Player > Android:
- Scripting Backend: IL2CPP; Target Architectures: ARM64 (required by Google Play)
- Minimum API level: 26 (Android 8); Target API: Play's current requirement
- Graphics APIs: Vulkan first, OpenGLES3 fallback (disable Auto Graphics API)
- Color Space: Linear (drop to Gamma only if Low-tier tests demand it)
- Managed Stripping Level: Medium/High (test for stripped types)
- Active Input Handling: Input System Package (New)
- Orientation: Landscape Left/Right only

Build Profiles > Android: "Build App Bundle (Google Play)" ON for AAB, OFF for a test APK.
Publishing Settings: create a keystore (keep it out of git, back it up).

Graphics: create a URP asset, assign it in Project Settings > Graphics and in each Quality level.
Disable Opaque/Depth Texture unless a feature needs them.
