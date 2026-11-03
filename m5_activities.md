# Module 5: Activities - Comprehensive Context File

## 1. Objectives & Overview

* **Target Learning Outcomes:**

  * Describe what Android activities are (similar to windows in desktop applications).

  * Understand the activity life cycle and its state transitions.

  * Identify different methods/callbacks associated with the activity life cycle.

  * Create and configure an activity using both Java and Kotlin.

* **Core Definition:** An Android activity represents a single screen with a user interface. An application typically starts with a main activity and can launch additional activities. Activities are subclasses of `android.app.Activity` (or `AppCompatActivity`).

## 2. Activity Life Cycle & Methods

An activity goes through several life cycle states managed by the Android OS framework through callback methods:

| Method / State | Description | 
| ----- | ----- | 
| **`onCreate()`** | Called when the activity is first created. Used for initialization, setting content views, and binding UI components. | 
| **`onStart()`** | Called when the activity becomes visible to the user. | 
| **`onResume()`** | Called when the activity starts interacting with the user (activity is in the foreground and running). | 
| **`onPause()`** | Called when the current activity is being paused (losing focus) and another activity comes into the foreground. The paused activity cannot receive user input. | 
| **`onStop()`** | Called when the activity is no longer visible to the user. | 
| **`onDestroy()`** | Called before the activity is destroyed by the system (due to finishing or process termination). | 
| **`onRestart()`** | Called when the activity restarts after being stopped, before calling `onStart()`. | 

## 3. Creating an Activity in Java

### Java Activity Class Structure

```java
package com.jenkov.myfirstandroidapp;

import android.app.Activity;
import android.os.Bundle;

public class MyFirstAndroidActivity extends Activity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        // Load UI components from res/layout/activity_main.xml
        setContentView(R.layout.activity_main);
    }
}

```

### Android Manifest Registration

All activities must be declared in the `AndroidManifest.xml` file inside the `<application>` element:

```xml
<manifest ...>
    <application ...>
        <activity android:name=".ExampleActivity" />
    </application>
</manifest>

```

## 4. Creating an Activity in Kotlin

### Kotlin Activity (`MainActivity.kt`)

```kotlin
package com.example.kotlinhelloworld

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}

```

### Layout XML (`activity_main.xml`)

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello Android!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

```