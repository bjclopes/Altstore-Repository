# YouMod Repo

Automated YouMod IPA builds delivered straight to your AltStore, SideStore, or Feather. 100% no need to fork GitHub repos or find your own decrypted IPA files!

---

## How to Add This Repo

1. Open **AltStore / SideStore / Feather** on your device
2. Navigate to **Sources** or **Repos**
3. Tap **+** and paste the URL below:

```
https://raw.githubusercontent.com/bjclopes/Altstore-Repository/main/apps.json
```

4. YouMod will appear under Browse — tap **Get** to install

> **Note:** You must have a signing method set up (AltStore, SideStore, Feather, Signulous, etc.) to install the IPA.

---

## Currently Supported

| Description | Info |
|---|---|
| **YouTube version** | 21.47.6 |
| **YouMod version** | 2.1.0 (pre-release 8574c53) |
| **Last built** | November 27, 2026 |
| **Min iOS** | 14.0 |

---

## Included Tweaks

Only these tweaks are compiled in — nothing else. YTVideoOverlay is a hard runtime
dependency of YTUHD (its reload button registers through YTVideoOverlay), so it rides along.

| Tweak | Description |
|---|---|
| [YouMod](https://github.com/Tonwalter888/YouMod) | The core tweak. Ad removal, background playback, UI customisation, and more — without a paywall. |

---

## How Automatic Builds Work

This repo builds and publishes a new YouMod IPA automatically.

```
Scheduled workflow checks for a new commit on YouMod's pre-release branch (every 2 hours)
        ↓
config.yml is bumped to the new commit and version
        ↓
GitHub Actions compiles the tweaks from source (YouMod from that exact commit)
        ↓
cyan injects them into the decrypted YouTube IPA
        ↓
apps.json and a GitHub release updated with the new version, size and changelog
```

The YouTube version and its decrypted IPA URL are pinned in [`config.yml`](config.yml) — edit either value and push to trigger a new build manually.

A failed build is retried by the next scheduled check, so the repo does not get stuck on a broken version.

---

## 🙏 Credits

| Developer | Tweaks |
|---|---|
| [Tonwalter888](https://github.com/Tonwalter888) | YouMod, YTUHD |
| [asdfzxcvbn](https://github.com/asdfzxcvbn) | cyan (IPA injection tool) |
