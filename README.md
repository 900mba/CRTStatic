# No Signal — CRT static app

A full-screen "no signal" static generator for Android, like an old CRT
tuned to a dead channel. Runs on any phone (minSdk 21 = Android 5.0+).

## How to build it

1. Install **Android Studio** (free, from developer.android.com/studio).
2. Open this folder (`CRTStatic/`) as a project — File → Open.
3. Let Gradle sync (first time takes a few minutes, downloads the build tools).
4. Plug in your Android phone via USB with USB debugging enabled, or use an emulator.
5. Click Run ▶. That's it — installs and launches the app.

To get an installable APK without a cable: Build → Build Bundle(s)/APK(s) →
Build APK(s), then copy the .apk from `app/build/outputs/apk/debug/` onto
your phone and tap it (you'll need to allow "install unknown apps" once).

## What's in the box

- Tap the faint gear icon top-right for settings.
- Grain size, contrast, scanline opacity, roll/hum-bar speed, refresh rate,
  4 color modes (mono, RGB snow, green phosphor, amber phosphor), vignette
  toggle, "NO SIGNAL" text toggle, keep-screen-on toggle.
- Everything's drawn to a small offscreen bitmap and scaled up, so it's
  cheap on battery/CPU even on old hardware.

## Ideas for extending it later

- Channel-tuning sound (static hiss loop, maybe with a "click" when you
  tap to change "channel").
- A drag gesture to simulate manually adjusting a rabbit-ear antenna,
  temporarily clearing the static into a ghost image before it fades back.
- Barrel/pincushion screen curvature via a fragment shader (RenderEffect
  on Android 12+, or a GLSurfaceView for wider compatibility).
- RGB channel misalignment (chromatic aberration) for an off-tracking VHS look.
- A widget/live-wallpaper version so it can run behind your home screen.
- Auto screen-off timer so it doesn't run all night by accident.
