# Module 1: Introduction to Android - Comprehensive Context File

## 1. Objectives & Overview
* **Target Learning Outcomes:**
  * Discuss the origins and history of Android.
  * Recognize market presence and user share of Android.
  * Differentiate various Android versions, codenames, and API levels (from Android 1.0 to Android 17).
  * Describe core Android features.
  * Understand Android software architecture and its layers.
* **Core Definition:** Android is a mobile operating system based on the Linux kernel, originally developed by Android Inc., which was acquired by Google in 2005. The Android OS is open-source and free, offering reduced cost of development, higher success ratios, inter-app integration, and a rich development environment with a large developer/community reach.

---

## 2. Android Versions, Codenames, Release Years, and API Levels

| Version | Codename / Internal Name | Release Date | API Level | Key Features & Highlights |
| :--- | :--- | :--- | :--- | :--- |
| **Android 1.0** | (Unnamed / No official codename) | Sept 2008 | API 1 | First commercial version (HTC Dream). Google Maps, Camera, Gmail/Contacts sync, Web Browser, Wi-Fi & Bluetooth support. |
| **Android 1.1** | (Unnamed / Petit Four) | Feb 2009 | API 2 | Added save attachment in messages; reviews and details when searching businesses on maps. |
| **Android 1.5** | Cupcake | Apr 2009 | API 3 | First official dessert codename. UI updates, YouTube/Picasa upload services, MPEG-4 video recording, browser copy-paste. |
| **Android 1.6** | Donut | Sept 2009 | API 4 | Large screen size support, Gallery and Camera features, improved system app speed. |
| **Android 2.0 - 2.1** | Eclair | Oct - Dec 2009 | API 5-7 | UI updates, live wallpapers, Bluetooth 2.1 support, improved Google Maps, minor API changes. |
| **Android 2.2** | Froyo | May 2010 | API 8 | Animated GIF support, Wi-Fi hotspot functionality, speed improvements, browser file upload, numeric/alphanumeric passwords. |
| **Android 2.3 - 2.4** | Gingerbread | Dec 2010 | API 9-10 | Launched on Nexus S (co-developed with Samsung). Improved copy-paste, updated UI, social networking support, easy keyboard usage. |
| **Android 3.0 - 3.2** | Honeycomb | Feb - Aug 2011 | API 11-13 | Tablet-focused. Gmail app improvements, 3D UI, media sync from SD card, Google eBooks, Google Talk video chat, Adobe Flash support, high-performance Wi-Fi locking, Chinese handwriting. |
| **Android 4.0** | Ice Cream Sandwich | Oct 2011 | API 14-15 | Synthesized Honeycomb for phones. Improved text input/spell check, Wi-Fi Direct, photo decor, keyboard corrections, Face Lock, improved video recording resolution, up to 16 browser tabs. |
| **Android 4.1 - 4.3** | Jelly Bean | July 2012 | API 16-18 | Introduced Google Now, voice search/typing, smooth UI, camera improvements, multi-user accounts (tablets), 4K support, Bluetooth Low Energy, native emojis. |
| **Android 4.4** | KitKat | Sept 2013 | API 19 | Screen recording, "OK Google" hotword detection (hands-free Google Now), GPS support, offline music, UI updates for maps/alarms, emojis in Google keyboard. |
| **Android 5.0 - 5.1** | Lollipop | Nov 2014 | API 21-22 | Android Runtime (ART) support, battery saver, Material Design UI, multi-SIM support, high-definition voice calls. |
| **Android 6.0** | Marshmallow | May 2015 | API 23 | Fingerprint authentication, USB Type-C support, Sleep Mode (battery saver), runtime app permission model (OPT requests), new emojis. |
| **Android 7.0 - 7.1** | Nougat | Aug 2016 | API 24-25 | Native split-screen / multi-window multitasking, data saver feature, storage manager improvements, display touch improvements. |
| **Android 8.0 - 8.1** | Oreo | Aug 2017 | API 26-27 | Picture-in-Picture (PIP) support, multi-display support, Google Play support, adaptive icons, improved notification system. |
| **Android 9.0** | Pie | Aug 2018 | API 28 | Screenshot button, Lockdown mode for biometrics, display cutout support, Adaptive Battery prediction, Adaptive Brightness based on habits. |
| **Android 10** | Queen Cake (Quince Tart) | Sept 2019 | API 29 | Shift to numerical branding. Background location and file access permissions, sharing shortcuts, dynamic depth photo format (post-capture blur), system-wide dark theme. |
| **Android 11** | Red Velvet Cake | Sept 2020 | API 30 | Native screen recording, muting notifications during video, increased touch sensitivity, notification history, auto-revoke permissions, conversations & bubbles. |
| **Android 12** | Snow Cone | Oct 2021 | API 33 | Scrolling screenshots, AppSearch, improved auto-rotate, easier Wi-Fi sharing, one-handed mode, rich content insertion, game mode APIs. |
| **Android 12L** | Snow Cone v2 | 2022 | API 32 | Specialized feature release focusing on large screens and foldables. |
| **Android 13** | Tiramisu | Aug 2022 | API 33 | Improved security, reading mode, digital car keys, native LE Bluetooth support, Material You theme options, QR code scanner support, photo picker, per-app language preferences. |
| **Android 14** | Upside Down Cake | Oct 2023 | API 34 | Smarter scaling/large fonts, notification flashes, photo/video access restrictions, protected PIN, data protection, regional preferences, predictive back gestures, Health Connect. |
| **Android 15** | Vanilla Ice Cream | Sept 2024 | API 35 | Privacy Sandbox, Health Connect, file integrity, partial screen sharing, in-app camera controls, dynamic performance, sensitive notifications. |
| **Android 16** | Baklava | June 2025 | API 36 / 36.1 | Live Updates foundation (ProgressStyle notifications for ongoing activities), adaptive apps (large-screen resizability target behavior), default predictive back preview animations. |
| **Android 17** | Cinnamon Bun | June 2026 | API 37 | AppFunctions (structured functions for assistants/agents), adaptive-first large screen requirements, windowed interaction (App Bubbles, Bubble Bar, interactive desktop PiP). |

---

## 3. Android Architecture
The Android software stack consists of 5 main layers:

1. **Applications:** Top layer containing native and user-installed apps (Home, Contacts, Camera, SMS, Alarm, Phone, Clock, Email, Calendar, Music, Gallery).
2. **Android Framework:** Provides higher-level services used by applications via Java/Kotlin APIs. Key managers include:
   * Activity Manager
   * Package Manager
   * Window Manager
   * Notification Manager
   * Content Providers
   * View System
   * Location Service & NFC Service
3. **Android Runtime (ART):** Includes the Dalvik Virtual Machine (DVM) / runtime environment, Zygote (process spawning), Android Debug Bridge (ADB), and Core Libraries.
4. **Platform Libraries (C/C++):** Built on C/C++ libraries exposed through application framework services:
   * Media Framework, OpenGL, Graphics, SGL
   * SSL, SQLite, Surface Manager, FreeType
5. **Linux Kernel:** The foundational core providing core OS functions (memory management, security, process management) and hardware drivers:
   * Display, Wi-Fi, Audio, Bluetooth drivers
   * Camera, USB, Binder IPC, and Memory drivers

---

## 4. Key Takeaways & Naming Conventions
* **Naming Note:** Android 1.0 and 1.1 had no official public dessert codenames. Android 1.5 through Android 9 utilized dessert codenames alphabetically (Cupcake through Pie). Android 10 onward uses numerical public branding while maintaining internal dessert codenames (e.g., Quince Tart, Red Velvet Cake, Snow Cone, Tiramisu, Upside Down Cake, Vanilla Ice Cream, Baklava, Cinnamon Bun).