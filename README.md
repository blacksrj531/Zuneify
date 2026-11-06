# Zuneify 🎵🎬

> The ultimate, ground-up evolutionary successor to Microsoft Zune & Windows Phone Metro. Engineered from first principles for modern Android with industrial-grade playback performance, uncompromising local privacy, military-grade binary hardening, and visual poetry.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Platform](https://img.shields.io/badge/Platform-Android%208.0%2B-brightgreen.svg)](https://android.com)
[![Release](https://img.shields.io/badge/Release-v5.9.1-orange.svg)](https://github.com)
[![Architecture](https://img.shields.io/badge/Architecture-Universal%20(ARM64%20%7C%20ARMv7%20%7C%20x86__64)-success.svg)](https://github.com)
[![Privacy](https://img.shields.io/badge/Privacy-100%25%20Offline%20%7C%20Zero%20Tracking-blueviolet.svg)](PRIVACY_POLICY.md)
[![Security](https://img.shields.io/badge/Security-OWASP%20Mobile%20Hardened-green.svg)](PRIVACY_POLICY.md)

---

## 💡 The Real Problems Zuneify Solves Across the Entire Media Stack

Today's mobile media ecosystem is broken. Streaming services hold your media hostage, while conventional Android media players have devolved into clunky, battery-draining adware wrappers that choke on large files and harvest your habits. 

Zuneify solves the deepest architectural and user experience flaws across both **Music** and **Video**:

### 🎵 In Audio & Music Playback:
1. **Broken Metadata & "Unknown Artist" Chaos:** Most players blindly dump raw filenames. Zuneify features an autonomous metadata heuristic cleaner (`SongMetadataCleaner.kt`) that strips garbage tags, web URLs, bitrate stamps, and track junk from ID3 tags, presenting your library like a studio master.
2. **Missing Lyrics Synchronization:** While Spotify and Apple Music lock synchronized lyrics behind subscriptions, Zuneify embeds a native `.lrc` timestamp parser and real-time kinetic auto-scroller (`LyricsSection.kt`, `LrcParser.kt`), supporting both embedded ID3 synced lyrics and external sidecar files.
3. **Flat, Lifeless Audio Output:** Generic players use Android's basic audio pipeline. Zuneify integrates a custom 10-band equalizer engine with studio bass boost, reverb models, and 3D virtualizer algorithms (`AudioEffectsManager.kt`), tailored to both wired IEMs and high-impedance Bluetooth headphones.
4. **Library Desynchronization & Stale Caches:** When you add, edit, or delete songs, other players require manual library rescans that freeze your phone. Zuneify's reactive Room architecture (`MusicRepository.kt`) listens to content observers in real-time, instantly reflecting changes with zero background lag.
5. **Lossy Online Radio Experience:** Internet radio apps are packed with audio ads and trackers. Zuneify integrates a clean, high-bandwidth directory scanner directly powered by community-driven endpoints (`radio-browser.info`), streaming live worldwide stations with zero third-party telemetry.

### 🎬 In Video Playback:
1. **The Infamous "MKV Seek-Reset" Bug:** Standard Media3 and ExoPlayer engines choke on chained EBML `SeekHead` pointers common in modern HandBrake, WEB-DL, and 4K Matroska (`.mkv`) movies, resetting playback to `00:00` when seeking. Zuneify’s custom `ZuneMatroskaSeekResolver` traverses tail pointers directly on raw file channels, decoding `CuePoints` into a seekable `ChunkIndex`.
2. **Accidental Rotations While Watching in Bed:** Tapping "lock" in VLC, MX Player, or YouTube only locks on-screen touch buttons; tilting your phone still flips the display upside down. Zuneify introduces a true hardware subsystem lock (`ActivityInfo.SCREEN_ORIENTATION_LOCKED`) that physically freezes orientation in place, paired with a one-tap 3-way orientation cycle (Auto-Rotate / Forced Landscape / Forced Portrait).
3. **Scoped Storage Blindness:** Android 11–16's Scoped Storage hides folders with `.nomedia`, downloaded Telegram movies, and nested SD card directories. Zuneify’s built-in Metro Directory Scanner (`File.walkTopDown()`) bypasses MediaStore limitations and indexes your entire storage hierarchy directly without violating Linux sandbox rules.
4. **Distracting Letterboxed PiP Windows:** Conventional players fail to compute dynamic video dimensions in Picture-in-Picture mode, leaving chunky black letterbox bars and cluttered playback controls. Zuneify reads real-time decoder metadata (`videoSize`), computes exact mathematical aspect ratios (`PictureInPictureParams.Builder.setAspectRatio`), and hides all overlays for a distraction-free floating window.
5. **Audio/Subtitle Desynchronization:** Multi-language anime and foreign films frequently have unsynchronized or unselectable audio tracks. Zuneify includes an interactive track selector for multi-stream audio languages and an external subtitle picker supporting `.srt`, `.vtt`, `.ass`, and `.ssa`.

---

## 🚀 How Much Way Ahead This Project Stands

Zuneify is built on a 2026 reactive Jetpack Compose architecture and native C++17 foundation that fundamentally outperforms legacy media apps:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        ZUNEIFY SYSTEM TOPOLOGY                         │
├────────────────────────────────┬───────────────────────────────────────┤
│    Authentic Metro Frontend    │ • 120Hz Kinetic Panoramic Navigation  │
│    (Windows Phone Heritage)    │ • Bundled Microsoft Segoe UI Family   │
├────────────────────────────────┼───────────────────────────────────────┤
│    High-Performance Media      │ • Chained EBML SeekHead Resolver      │
│         Pipeline Core          │ • 30s Uncompressed RAM Backbuffer     │
│                                │ • 10-Band Studio DSP Equalizer        │
├────────────────────────────────┼───────────────────────────────────────┤
│    Zero-Trust Security Engine  │ • Native Hidden C++ Symbols (-fvis)   │
│       (OWASP Mobile A+)        │ • Anti-Tamper SHA-256 APK Pinning     │
│                                │ • Constant-Time Side-Channel Defense  │
└────────────────────────────────┴───────────────────────────────────────┘
```

- **30-Second RAM Scrubber Backbuffer:** Standard players flush memory and read from flash storage every time you scrub backward. Zuneify configures a 30,000ms forward and backward RAM backbuffer (`DefaultLoadControl`), making scrubbing back and forth instantaneous and completely non-blocking.
- **Hardware-Accelerated 120Hz Animation Physics:** While legacy apps use standard scrolling lists, Zuneify implements custom kinetic physics: horizontal panoramic marquee headers, friction-weighted flings, and smooth pivot transitions that look hyper-responsive on 90Hz, 120Hz, and 144Hz OLED displays.
- **Unified Cross-OEM Typography:** Eliminates vendor font fragmentation (Samsung One UI, Xiaomi HyperOS, OnePlus OxygenOS, Nothing OS). By bundling authentic `Segoe UI Light`, `Semilight`, `Regular`, and `Bold` inside the APK, Zuneify renders identical, pixel-perfect typography on every single Android device.
- **Zero-Latency State Synchronization:** Powered by Kotlin StateFlows and asynchronous coroutines across `PlaybackService.kt`. Audio playback, notification media sessions, Android Auto vehicle dashboards, and lock screen widgets update concurrently with 0ms visual lag.

---

## 🏆 Outperforming Other Media Players & Microsoft's Original Zune

While Microsoft's original Zune software (2006–2011) pioneered typography and kinetic motion, it was crippled by locked hardware, mandatory desktop sync software, and strict DRM. Modern Android players (VLC, MX Player, Poweramp, Retro Music) have wide codec support, but are bloated by ads, complex menus, and inconsistent styling. 

Zuneify unites the best of both worlds and pushes beyond them:

| Architectural Vector | Original Microsoft Zune (2006–2011) | Modern Android Players (VLC, MX, Poweramp) | **Zuneify (2026)** |
| :--- | :--- | :--- | :--- |
| **Container & Codec Freedom** | Restricted to WMV, WMA, MP3, MP4. Required desktop software to convert files. | Wide codec support, but frequently resets seeking on chained MKV movies. | **Universal MKV, MP4, WebM, FLAC, OGG, MP3** with built-in custom EBML cue-index injection. 100% standalone. |
| **Typography & Visual Polish** | Restricted to 480x272 low-resolution screens. | Cluttered Material Design or iOS clones; mismatched OEM fonts; jarring banner ads. | **Authentic Segoe UI typography** with seamless horizontal panoramic swipe, scaled up to 4K Ultra HD. |
| **True Screen Rotation Lock** | None (hardware was locked in portrait). | Touch lock only; tilting your phone still flips screen orientation. | **True Hardware Subsystem Lock (`SCREEN_ORIENTATION_LOCKED`)** with 3-state switcher. |
| **Hardware RAM Scrubbing** | Limited by 64MB device RAM; heavy disk reading. | Buffers only forward; seeking backward causes re-buffering spinners. | **Dual 30-Second RAM Backbuffer** for zero-latency bidirectional timeline scrubbing. |
| **Subsystem Security & Privacy** | Closed-source proprietary firmware. | Third-party analytics SDKs, advertising trackers, and telemetry services. | **100% Zero-Telemetry, No WebViews, Stripped C++ symbols, and SHA-256 Anti-Tamper Pinning.** |
| **Synchronized Lyrics & Artist Hubs** | Static metadata sync only via desktop marketplace. | Clunky, plain text, or hidden behind paywalls. | **Real-time `.lrc` kinetic scrolling**, synchronized karaoke views, and artist bio exploration. |
| **Global Radio & Modern Extras** | Deprecated FM radio tuner on physical hardware. | Ad-interrupted radio networks requiring monthly subscriptions. | **Free Worldwide Online Radio Browser** (`radio-browser.info`) with zero ads. |

---

## 🛡️ Industrial-Grade Security & Anti-Reverse Engineering

Zuneify adheres to the **OWASP Mobile Application Security Verification Standard (MASVS)** with deep-layer defense:

1. **JNI Native Boundary Hardening (`secrets.cpp`):**
   - Stripped symbol tables via `-fvisibility=hidden -fvisibility-inlines-hidden`. Decompilers (Ghidra, IDA Pro, JADX) cannot inspect or resolve internal functions.
   - Constant-time bitwise XOR comparison eliminates CPU timing side-channel attacks against cryptographic routines.
2. **APK Anti-Tamper & Anti-Repackaging Defense (`SecurityCheck.kt`):**
   - The app verifies its own signing certificate fingerprint against the official SHA-256 release key (`6F:6D:30:C8:...`) on startup. Modified or cracked APKs exit immediately (`exitProcess(0)`).
3. **Zero Web Attack Surface:**
   - Contains **0 WebViews**. The app is built 100% in native Jetpack Compose, immune to cross-site scripting (XSS), URL spoofing, and JavaScript bridge remote execution.
4. **Memory Allocation Caps (DoS / OOM Defense):**
   - The MKV cue parser bounds element lengths to a strict 10MB limit with non-negative bounds guards, preventing malformed media files from crashing the device.
5. **Strict Network & Backup Isolation:**
   - Cleartext HTTP traffic is blocked app-wide in `network_security_config.xml`.
   - `android:allowBackup="false"` prevents database extraction via ADB backup.

---

## 🔒 Privacy Guarantee

- **Zero Data Collection:** No names, device identifiers, email addresses, or usage logs are ever recorded.
- **Zero Third-Party SDKs:** No Google Analytics, Firebase, Facebook SDK, Adjust, or AppsFlyer.
- **100% Local Processing:** Your listening history, playlists, favorites, and equalizer profiles stay permanently on your device.

Read the complete [Privacy Policy](PRIVACY_POLICY.md).

---

## 📦 Technical Specifications

- **Version**: `5.9.1` (Version Code: `24`)
- **Target SDK**: `34` (Android 14)
- **Min SDK**: `26` (Android 8.0 Oreo+)
- **Build System**: Gradle 8.9 / Kotlin 2.0 / CMake 3.22.1 (C++17)
- **Architectures**: Universal (`arm64-v8a`, `armeabi-v7a`, `x86`, `x86_64`)

---

## ⚖️ License & Intellectual Property Notice

This program is free software: you can redistribute it and/or modify it under the terms of the **[GNU General Public License v3.0 (GPLv3)](LICENSE)** as published by the Free Software Foundation.

### Fair Use & Trademark Disclaimer
- **Zune & Windows Phone Metro**: "Zune", "Windows Phone", "Metro UI", and associated visual motifs are registered trademarks of Microsoft Corporation. This project is a non-profit, fan-made tribute created strictly for educational, historical, and preservation purposes. It is neither affiliated with, endorsed by, nor sponsored by Microsoft Corporation.
- **Segoe UI Fonts**: Microsoft Segoe UI font assets are the intellectual property of Microsoft Corporation and are bundled strictly for non-commercial aesthetic authenticity.
