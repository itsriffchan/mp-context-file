# Module 2: Android Studio - Comprehensive Context File

## 1. Objectives & Overview

* **Target Learning Outcomes:**
  * Identify prerequisites for Android Studio installation.
  * Identify system requirements for Windows and Mac.
  * Create an Android project in Android Studio.
  * Familiarize with the Android Studio IDE interface.
  * Run the first Android application on a real device or emulator.

* **Core Prerequisites:**
  * **JDK (Java Development Kit):** Required for compiling and running Java/Kotlin code.
  * **Android Studio:** Official Integrated Development Environment (IDE) for Android development.

---

## 2. System Requirements

### Windows
* **Operating System:** Microsoft Windows 7 / 8 / 10 (32- or 64-bit).
* **RAM:** 3 GB minimum, 8 GB recommended (plus 1 GB for the Android Emulator).
* **Disk Space:** 2 GB available minimum, 4 GB recommended (500 MB for IDE + 1.5 GB for Android SDK and emulator system image).
* **Screen Resolution:** $1280 \times 800$ minimum.

### Mac
* **Operating System:** Mac OS X 10.10 (Yosemite) or higher, up to 10.13 (macOS High Sierra).
* **RAM:** 3 GB minimum, 8 GB recommended (plus 1 GB for the Android Emulator).
* **Disk Space:** 2 GB available minimum, 4 GB recommended (500 MB for IDE + 1.5 GB for Android SDK and emulator system image).
* **Screen Resolution:** $1280 \times 800$ minimum.

---

## 3. Creating an Android Project

1. Launch Android Studio and click **Start a new Android Studio project** (or select `File > New > New Project` if an IDE project is already open).
2. In the **Choose your project / Templates** window, select **Empty Activity** (or *Empty Views Activity*). Click **Next**.
3. In the **Configure your project** window, enter:
   * **Name:** "My First App" (or "My Application")
   * **Package name:** `com.example.myfirstapp` (or `com.example.myapplication`)
   * Check **Use AndroidX artifacts** (if available).
   * **Language:** Select **Java** (or Kotlin).
   * **Minimum SDK:** Select target API (e.g., API 24: Android 7.0 Nougat or API 16: Android 4.1 Jelly Bean).
4. Click **Finish**.

---

## 4. Code Samples Present in Module 2

### MainActivity.java
The default generated Java activity code for `MainActivity`:

```java:MainActivity.java
package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```

---

## 5. Android Studio Interface Components

Android Studio provides a unified workspace divided into key functional areas:

1. **Toolbar:** Allows carrying out a wide range of actions, including running apps and launching Android tools.
2. **Navigation Bar:** Helps navigate through the project structure and open files for editing in a compact view.
3. **Editor Window:** Where code and layouts are created and modified. Dynamically changes depending on the file type (e.g., Layout Editor for XML files, Code Editor for Java/Kotlin).
4. **Tool Window Bar:** Runs around the edges of the IDE window containing buttons to expand or collapse individual tool windows.
5. **Tool Windows:** Access specific tasks such as Project management, Search, Version Control, Debugger, and Terminal.
6. **Status Bar:** Displays project status, IDE status, warnings, and error messages.

---

## 6. Running Your Application

* **Run on Real Device:**
  1. Connect your Android phone to the computer via USB.
  2. Enable **Developer Options** and turn on **USB Debugging** on the physical device.
  3. Click the Run button in Android Studio and select the connected physical device.
* **Run on Emulator:**
  1. Navigate to **Device Manager** and select **Create Device**.
  2. Choose a device definition (e.g., Pixel 2, Pixel 6) and screen size.
  3. Select the desired Android SDK system image version.
  4. Finish setup and launch the virtual device.