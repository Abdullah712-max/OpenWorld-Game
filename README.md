# OpenWorldLife - Phase 1 foundation
Original open-world life/business/action game. Engine: Unity 6 LTS + URP. Target: Android (APK/AAB).

## What exists
- Core: EventBus (typed pub/sub), ServiceLocator, GameClock (24h cycle with hour/day events)
- Optimization: QualityProfile (LOW..ULTRA incl. NPC/traffic budgets), DeviceProfiler (auto-recommend), QualityManager
- Bootstrap: initializes services before any scene loads; DebugHud for on-device checks
- One assembly definition per future system (Player, Vehicles, NPC ... Save), all referencing Core only

## Run it
1. Unity Hub > New project > Universal 3D (URP), Unity 6 LTS.
2. Copy Assets/_Game into the project's Assets/. Install the Input System package.
3. Open any scene, add an empty GameObject with DebugHud, press Play.
4. Android: follow Docs/ANDROID_SETUP.md, then File > Build Profiles > Android.

## Rules
Systems depend on Core only and talk through EventBus/ServiceLocator. No direct cross-system references.

STATUS: written but not compiled or run (no Unity in the authoring environment). Expect small fixes on first import.
