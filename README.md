# slot. Android 11 patches (Morphe)

Morphe patch bundle that lets **slot. for Android** (`fyi.slot.konkr`, by Baggio94)
install on **Android 11** by lowering `minSdkVersion` from 31 to 30.

Unofficial and untested on a real device. Not affiliated with Morphe or the slot. author.

## 🩹 Patches list

<!-- PATCHES_START EXPANDED -->

<!-- Do not modify this section by hand. The patch list is generated when release.yml creates a new release. -->

#### The patch list is generated automatically when a release is created.

<!-- PATCHES_END -->

The single patch, **Android 11 support**, sets `android:minSdkVersion="30"` in AndroidManifest.xml.

## Known limitations
- The Bluetooth status icon needs the Android 12-only BLUETOOTH_CONNECT permission, so it stays hidden on Android 11.
- The app's native emulator cores were built against API 31. If one uses a function Android 11 lacks, the app may crash when that core loads.
- Only the release APK (v2.0.0) is targeted. Edit `Constants.kt` if its versionName differs.

## Build
Needs Java 17+ and a GitHub token with `read:packages` (Morphe's plugin is on GitHub Packages).

    export GITHUB_ACTOR=your-username
    export GITHUB_TOKEN=your-token
    ./gradlew buildAndroid        # -> patches/build/libs/patches-*.mpp

Apply the `.mpp` with Morphe Desktop, or publish via the template's `release.yml`
and add the repo as a patch source in Morphe Manager.

Based on https://github.com/MorpheApp/morphe-patches-template (GPLv3, see NOTICE).
