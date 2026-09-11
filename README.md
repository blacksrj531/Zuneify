# 🎵 Zuneify

**Zuneify** (formerly Zune Rebirth) is a premium, modern Android media player meticulously designed to resurrect the legendary **Zune HD / Windows Phone Metro** aesthetic. Built from the ground up with native Kotlin and Jetpack Compose, it blends the beloved, immersive typography-driven UI of the past with cutting-edge Android media technologies.

## 💡 The Inception & Skills Implementation
**The Idea:** The Zune HD and early Windows Phone devices had one of the most beautiful, typography-heavy, and fluid user interfaces in digital history. I wanted to bring that exact feeling back to life for modern Android devices, not just as a visual theme, but as a fully functional, high-performance daily driver for media playback. 

**Skills Executed:** Bringing this idea to life required deeply integrating several advanced Android development disciplines:
* **Advanced Jetpack Compose:** Architected a complex "Panorama" side-scrolling UI shell, heavily utilizing custom state management, nested scrolling, and bespoke typography rendering to perfectly mimic the Metro design language.
* **Media3 / ExoPlayer Architecture:** Built robust foreground `MediaSessionServices` to handle audio focus, background playback, and seamless state persistence that survives app reboots.
* **Asynchronous Networking:** Engineered a background coroutine engine to poll the GitHub REST API, process JSON version tags, and stream `.apk` file downloads for Over-The-Air updates.
* **Lifecycle & Intent Routing:** Handled complex `PendingIntents`, Android FileProviders, and native Share Sheets to bridge the app seamlessly with the Android OS.

## ✨ Features

### 🎨 Authentic Metro UI Experience
* **Panorama Navigation:** A massive, side-scrolling pivot architecture that seamlessly glides between your Home, Music, Videos, Social, and Settings hubs.
* **Classic Typography:** True-to-era oversized, lightweight, lowercase headers wrapped in a pitch-black AMOLED UI with striking Zune Accent & Magenta highlights.
* **Immersive Visualizer:** The Now Playing screen features a live, breathing gradient background that reacts to the music, paired with real-time **Synced Lyrics**.

### 🎧 Advanced Audio Engine (Media3)
* **High-Fidelity Playback:** Powered by Google's ExoPlayer/Media3 for flawless playback across all standard local audio formats.
* **Audio Amplifier & Equalizer:** A built-in DSP engine to tweak your bass, treble, and vocal isolation directly inside the app.
* **System Integration:** Fully wired into the Android OS for Lockscreen controls, Bluetooth headset actions, and rich Notification Tray widgets.

### 🎬 Powerful Video Player
* **Gesture Controls:** Custom UI overlays allowing you to swipe for Volume, Brightness, and fast-forward seeking.
* **Picture-in-Picture (PiP):** Minimize your videos and watch them in a floating window while you navigate other apps.

### 🔄 In-App OTA Auto-Updater
* **GitHub Integration:** Zuneify autonomously pings the GitHub API on startup to check for the latest stable releases.
* **Silent Handoffs:** Downloads the `.apk` cleanly in the background with a Zune-styled progress bar and securely hands it off to the native Android Package Installer.
* **State Persistence:** The app flawlessly remembers exactly what song you were listening to before updating, and instantly resumes playback the moment the update finishes.

### 💬 Social & Smart Feedback
* **Developer Connect:** Direct integration to the creator's portfolio (`BLACKSRJ531`).
* **Smart Rating UI:** An interactive 5-star rating system. Low ratings safely redirect to private email support, while 4-5 star ratings trigger a Zune glow animation to collect your praise!

## 🛠️ Tech Stack
* **Language:** 100% Kotlin
* **UI Framework:** Jetpack Compose (Material3)
* **Media Engine:** AndroidX Media3 (ExoPlayer)
* **Concurrency:** Kotlin Coroutines & Flows
* **Network:** `HttpURLConnection` & GitHub REST API

## 📥 Installation
1. Navigate to the **[Releases](https://github.com/blacksrj531/Zuneify/releases/latest)** page.
2. Download the latest `zuneify.blacksrj.apps.apk` file.
3. Open the APK on your Android device (ensure "Install from Unknown Sources" is enabled).
4. Enjoy the music! (The app will handle all future updates automatically).

## 👨‍💻 Developer
Developed and maintained by **Soumya Ranjan Jena** (BLACKSRJ531).
* **Portfolio:** [blacksrj531.github.io/my_portfolio_531](https://blacksrj531.github.io/my_portfolio_531/)
* **LinkedIn:** [Soumya Ranjan Jena](https://www.linkedin.com/in/jenasoumyaranjan531/)

---

## ⚖️ Legal & Policies

**© 2026 Soumya Ranjan Jena (BLACKSRJ531). All Rights Reserved.**

### Copyright & Anti-Cloning Policy (STRICT)
The specific execution, codebase, logic, and architecture of **Zuneify** are the sole, exclusive intellectual property of the developer. By downloading, installing, or viewing this project, you are legally bound by the following strict terms:
* **No Cloning or Modification:** You are strictly **prohibited** from reverse-engineering, modifying, decompiling, or altering this `.apk` using APKTool, app cloners, or any other modification tools. You may not release any modded versions, replica apps, or reskinned versions of this application under your own name or your team's name.
* **Strict AI & Source Code Ban:** You must **NEVER** copy, paste, input, or upload any of this application's source code, architecture, or decompiled files into any Artificial Intelligence (AI) platform, LLM, or visualization tool for the purpose of analyzing, replicating, or modifying the codebase.
* **Explicit Consent Required:** Any modification, distribution, or analysis of this codebase requires explicit, written permission directly from Soumya Ranjan Jena.

**⚠️ PENALTY CLAUSE FOR UNAUTHORIZED USE:**
If you or your team are found violating these terms (including cloning the app, uploading the code to AI platforms, or distributing modified replicas without my written consent), you are legally subject to the following penalties:
1. You must pay a major, immediate financial penalty fine directly to the developer within **2 to 4 business days** of the violation being discovered.
2. Failure to pay the initial penalty fine within the 2-4 day window will result in a mandatory recurring penalty of **60,000 INR per month**, payable to Soumya Ranjan Jena every month for the duration of his lifetime. 

### Privacy Policy
**Zuneify respects your privacy 100%.** 
* **Zero Telemetry:** Zuneify is a local media player. It does not collect, store, or transmit your personal data, listening habits, or device information to any external servers. 
* **Local Storage:** Storage permissions are strictly used to scan and play the audio/video files already present on your local device.
* **Network Usage:** The `INTERNET` permission is exclusively used for the In-App Updater to ping the official GitHub API and process metadata.
* **Feedback:** Any feedback sent via the Social Rating tab is routed securely through your own native email client (Gmail). No silent background data harvesting occurs.

### Content Disclaimer (DMCA)
Zuneify is strictly a local media player and streaming client. The application itself does not host, provide, or distribute any copyrighted audio or video files. Users are entirely responsible for ensuring they have the legal right to consume the media they play through this application. 

### Limitation of Liability
This application is provided "as-is" without any warranties, express or implied. By installing Zuneify, you agree that the developer is not liable for any device damage, data loss, or other issues that may arise from its use.

### Official Distribution Warning
The only official and secure sources to download Zuneify are this official GitHub Repository and the developer's verified portfolio. Downloading this APK from unauthorized third-party mirrors is strictly discouraged and done at your own risk.

### Open-Source Acknowledgements
Zuneify is built utilizing several powerful open-source libraries, including Google's AndroidX Media3 (ExoPlayer) and Jetpack Compose. All third-party libraries remain the property of their respective owners under their associated open-source licenses.

---
*Disclaimer: Zuneify is a passion project and homage to the original Microsoft Zune interface. The UI design language is inspired by Microsoft, but the underlying application, codebase, and structural execution are entirely original and unaffiliated with Microsoft.*
