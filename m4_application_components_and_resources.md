# Module 4: Application Components and Resources - Comprehensive Context File

## 1. Objectives & Overview

* **Target Learning Outcomes:**
  * Understand Android application components and their specific roles.
  * Identify additional UI and structural components.
  * Recognize different Android resource directories and organization.
  * Access resources programmatically in code and declaratively in XML.

* **Core Definition:** Application components are the essential building blocks of an Android application. They are loosely coupled by the `AndroidManifest.xml` file, which describes each component and how they interact.

---

## 2. Core Application Components

| Component | Description | Implementation Class |
| :--- | :--- | :--- |
| **1. Activities** | Represent a single screen with a user interface to handle user interactions (e.g., list emails, compose email, read email). One activity is marked as the launch screen. | Subclass of `Activity` (`public class MainActivity extends Activity`) |
| **2. Services** | Handle long-running operations in the background without blocking user interaction (e.g., playing music, fetching network data). | Subclass of `Service` (`public class MyService extends Service`) |
| **3. Broadcast Receivers** | Respond to broadcast messages from other apps or the OS (e.g., notifying when data download is complete). Each message is broadcasted as an `Intent`. | Subclass of `BroadcastReceiver` (`public class MyReceiver extends BroadcastReceiver`) |
| **4. Content Providers** | Supply data from one application to others on request, managed via `ContentResolver`. Data can be stored in file systems, databases, etc. | Subclass of `ContentProvider` (`public class MyContentProvider extends ContentProvider`) |

---

## 3. Additional Components

1. **Fragments:** Represent a portion of user interface in an Activity.
2. **Views:** UI elements drawn on-screen (buttons, lists, forms, text views, etc.).
3. **Layouts:** View hierarchies that control screen format and appearance (`LinearLayout`, `ConstraintLayout`, etc.).
4. **Intents:** Messaging objects wiring components together.
5. **Resources:** External elements such as strings, constants, and drawables.
6. **Manifest (`AndroidManifest.xml`):** Configuration file for the application.

---

## 4. Android Resource Organization

Resources are static content maintained separately in subdirectories under the `res/` directory of the project. During compilation, the `R` class is generated, containing resource IDs for all available resources.

| Directory | Resource Type & Description |
| :--- | :--- |
| **`animator/`** | XML files defining property animations. Accessed via `R.animator`. |
| **`anim/`** | XML files defining tween animations. Accessed via `R.anim`. |
| **`color/`** | XML files defining state lists of colors. Accessed via `R.color`. |
| **`drawable/`** | Bitmaps (`.png`, `.jpg`, `.gif`), nine-patches, state lists, shapes, and animation drawables. Accessed via `R.drawable`. |
| **`layout/`** | XML files defining user interface layouts. Accessed via `R.layout`. |
| **`menu/`** | XML files defining application menus (Options Menu, Context Menu, Sub Menu). Accessed via `R.menu`. |
| **`raw/`** | Arbitrary files saved in raw form. Accessed via `Resources.openRawResource(R.raw.filename)`. Files in `assets/` require `Asset Manager`. |
| **`values/`** | Simple values (strings, integers, colors, dimensions, styles) defined within `<resources>`. Examples: `strings.xml`, `colors.xml`, `dimens.xml`, `styles.xml`. |
| **`xml/`** | Arbitrary XML configuration files read at runtime via `Resources.getXML()`. |
| **`font/`** | Font files (`.ttf`, `.otf`, `.ttc`) or XML font-family files. |

---

## 5. Accessing Resources in Code & XML

### Example 1: Accessing Drawables in Code
To access `res/drawable/myimage.png` and set it on an `ImageView`:
```java
ImageView imageView = (ImageView) findViewById(R.id.myimageview);
imageView.setImageResource(R.drawable.myimage);
```

### Example 2: Accessing String Resources in Code
Given `res/values/strings.xml`:
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="hello">Hello, World!</string>
</resources>
```
Set the text on a `TextView` object programmatically:
```java
TextView msgTextView = (TextView) findViewById(R.id.msg);
msgTextView.setText(R.string.hello);
```

### Example 3: Loading Layouts in an Activity (`onCreate`)
Given layout `res/layout/activity_main.xml`:
```java
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```

### Example 4: Accessing Resources in XML
Given `res/values/strings.xml`:
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="opaque_red">#f00</color>
    <string name="hello">Hello!</string>
</resources>
```
Use these resources directly in a layout XML file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<EditText xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:textColor="@color/opaque_red"
    android:text="@string/hello" />
```