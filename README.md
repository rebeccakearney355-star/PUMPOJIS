# Pumpojis

Floating sticker bubble for Android. Stickers (MOON, FOMO, WAGMI, RUG, LFG, LMAO) are already processed
(transparent background, watermark removed, 384px) in `app/src/main/res/drawable-nodpi/`.

## Heads up
GitHub Codespaces can BUILD the app but cannot RUN it: there is no phone screen or overlay there.
You build an APK, download it, and install it on your Android phone.

## Option A: build in GitHub Actions (easiest, nothing to install)
1. Make this folder the root of a GitHub repo and push to `main`.
2. Repo > Actions > "Build APK" > latest run > download the `pumpojis-debug-apk` artifact.
3. Unzip, send `app-debug.apk` to your phone, install it (allow "install unknown apps").

## Option B: build inside Codespaces
1. Open the repo in a Codespace (the `.devcontainer` installs Java 17, Gradle 8.7 and the Android SDK; first start takes a few minutes).
2. Run: `gradle assembleDebug`
3. Right-click `app/build/outputs/apk/debug/app-debug.apk` in the file explorer > Download.

## On your phone
Open Pumpojis, grant "Display over other apps", and the bubble appears.
- Tap bubble: open or close the sticker grid. Drag it anywhere; it snaps to the screen edge.
- Tap a sticker: copies it, then paste in Telegram or X.
- Long-press a sticker: share sheet (most reliable).
- Long-press the bubble, or tap Stop in the notification: close it.

## Swapping stickers later
Put new originals in a folder, then run `python3 tools/prep_stickers.py <in.png> <out.png>` per image
(cuts out the background, drops the watermark, shrinks to 384px) and save over the file in `drawable-nodpi/`.
# PUMPOJIS