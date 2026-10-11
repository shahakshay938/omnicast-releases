# OmniCast

OmniCast is a personal **live‑TV app** for **Android phones** and **Android TV**.

Browse and play live channels, search, move playback between your phone and TV,
watch two channels side‑by‑side (multi‑view), and keep watching in a floating
picture‑in‑picture window.

This repository hosts the installable builds. Every release has **two** files —
install the one that matches your device:

| File | Device |
|------|--------|
| `app-mobile-release.apk` | Android phones & tablets |
| `app-tv-release.apk` | Android TV / Google TV |

> They are separate apps (different package IDs). Installing the phone build on a
> TV, or vice‑versa, won't work — pick the matching file.

---

## Install on a phone

1. On the phone, open the [latest release](../../releases/latest) and download
   **`app-mobile-release.apk`**.
2. Tap the downloaded file. Android will ask to allow installs from this source —
   allow it, then tap **Install**.
3. Open **OmniCast**.

## Install on Android TV

Most TVs can't tap a downloaded file directly, so use one of these.

### Option A — a "Downloader" app (easiest, no computer)

1. Install a *Downloader*‑type app from your TV's app store.
2. In it, open the [latest release](../../releases/latest) and download
   **`app-tv-release.apk`**.
3. Install it when prompted, then open **OmniCast**.

### Option B — adb from a computer

1. On the TV: **Settings → System → About →** tap **Build** seven times to turn on
   Developer options, then enable **USB/Network debugging**. Note the TV's IP.
2. On the computer (with `adb` installed):
   ```bash
   adb connect <TV-IP>:5555
   adb install -r app-tv-release.apk
   ```
   Newer Android TVs use pairing instead:
   ```bash
   # Settings → Developer options → Wireless debugging → Pair device with code
   adb pair <TV-IP>:<pair-port>      # enter the 6‑digit code shown
   adb connect <TV-IP>:<connect-port>
   adb install -r app-tv-release.apk
   ```
3. **Turn Developer options back off**, then open **OmniCast** from the TV's apps.

---

## Updates

OmniCast checks this page when it starts and offers any newer version **inside the
app** — you normally won't need to come back here to update.

## Requirements & notes

- Android **8.0** or newer.
- These builds are distributed outside the Play Store, so the **first install**
  asks you to allow installs from the source. That's normal for sideloaded apps.
- Phone and TV can share one account.
