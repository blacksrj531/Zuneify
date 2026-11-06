# Privacy Policy & Security Standards for Zuneify

**Last Updated:** November 2026  
**Application:** Zuneify (`zuneify.blacksrj.apps`)  

Zuneify is built from the ground up as a privacy-first, offline-capable media player. We firmly believe your media library and listening habits belong exclusively to you.

---

### 1. Zero Data Collection & Zero Telemetry
- **No Personal Identifiable Information (PII):** Zuneify does not collect, log, track, or share names, email addresses, phone numbers, hardware serial numbers, or location data.
- **No Analytics / No Trackers:** There are no third-party tracking SDKs (e.g., Firebase Analytics, Google Analytics, Facebook SDK, Adjust, or AppsFlyer) embedded in this application.
- **No Advertising:** Zuneify is 100% ad-free.

---

### 2. Device Permissions & How They Are Used
Zuneify requests only the minimal set of permissions required to deliver local media playback:

| Permission | Purpose |
| :--- | :--- |
| `READ_MEDIA_AUDIO` / `READ_MEDIA_VIDEO` | To scan and index your local audio and video files across device storage. |
| `MANAGE_EXTERNAL_STORAGE` | Used exclusively by the in-app Metro Directory Browser to discover custom user-specified folders and `.nomedia` directories. We do not modify or delete files without explicit confirmation. |
| `FOREGROUND_SERVICE` & `FOREGROUND_SERVICE_MEDIA_PLAYBACK` | Required by Android to continue playing audio/video in the background, when the screen is turned off, and in Picture-in-Picture (PiP) mode. |
| `POST_NOTIFICATIONS` | To show playback notifications with playback controls (play, pause, next, previous) on your lock screen and notification shade. |
| `INTERNET` | Exclusively used to fetch online radio directory listings and stream user-selected internet radio stations (`radio-browser.info`) and to check for GitHub release updates. No user library data is ever sent over the network. |

---

### 3. Network Security & Data Transmission
- **Strict HTTPS/TLS 1.3:** Enforced by default across the entire app via Android Network Security Configuration.
- **Cleartext Traffic Policy:** Cleartext (HTTP) traffic is blocked everywhere except for community-maintained radio streaming streams that do not support HTTPS.
- **Zero Cloud Syncing:** Your playlists, favorites, playback history, equalizer settings, and folder selections are stored 100% locally on your device in private SQLite/Room databases.

---

### 4. Android Sandboxing & Local Storage Compliance
- **Storage Isolation:** Zuneify strictly respects the Android Linux kernel and Scoped Storage security model (`ext_data_rw`). The application does not attempt to inspect private app directories (`Android/data`).
- **Data Protection:** `android:allowBackup="false"` is enforced to prevent unauthorized extraction of app data via ADB or automated backup tools.

---

### 5. Open Source & Transparency
Zuneify is free and open-source software licensed under the [GNU General Public License v3.0 (GPLv3)](LICENSE). Anyone can inspect the complete source code to independently audit our security and privacy practices.

---

### 6. Contact & Support
If you have questions, feedback, or security vulnerability reports regarding Zuneify:
- **GitHub Issues:** Submit an issue directly on the official repository.
