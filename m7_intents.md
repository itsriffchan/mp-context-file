# Module 7: Intents - Comprehensive Context File

## 1. Objectives & Overview

* **Target Learning Outcomes:**

  * Discuss and understand what an Android Intent is and its uses.

  * Differentiate between Explicit and Implicit intents.

  * Apply intents in an Android application to launch components and navigate screens.

  * Submit and receive data between components using Intent Extras and Bundles.

* **Core Definition:** An Android Intent is a passive data structure holding an abstract description of an operation to be performed. It is used with `startActivity()` to launch an activity, `startService()` / `bindService()` to communicate with services, and `broadcastIntent()` to send broadcasts to receivers.

## 2. Types of Intents

### Explicit Intents
Explicit intents designate the target component by its specific class name. They are typically used for application-internal messages (e.g., launching a sister activity or subordinate service within the same app).

```java
// Explicit Intent by specifying class name
Intent i = new Intent(FirstActivity.this, SecondActivity.class);
startActivity(i);
```

### Implicit Intents
Implicit intents do not name a specific target component; the component name field is left blank. They declare an action to be performed, allowing components from other applications (like viewing contacts, opening a browser, or making a phone call) to handle the request.

```java
Intent read1 = new Intent();
read1.setAction(Intent.ACTION_VIEW);
read1.setData(ContactsContract.Contacts.CONTENT_URI);
startActivity(read1);
```

## 3. Transmitting Data with Intents

### Using Intent Extras (`putExtra`)
Data can be attached as key-value pairs directly to an Intent object using `putExtra()` and retrieved using `getExtra()` methods in the target component.

* **Sending Data:**
  ```java
  Intent intent = new Intent(this, NextActivity.class);
  intent.putExtra("USER_NAME", "John Doe");
  intent.putExtra("USER_ID", 21);
  startActivity(intent);
  ```

* **Receiving Data:**
  ```java
  Intent intent = getIntent();
  String userName = intent.getStringExtra("USER_NAME");
  Integer userId = intent.getIntExtra("USER_ID", 0);
  float userRating = intent.getFloatExtra("USER_RATING", 0.0f);
  ```

### Transmitting Data Using Bundles
A `Bundle` is a mapping from String keys to various parcelable/primitive values, allowing multiple key-value pairs or arrays to be passed together through an intent.

* **Sending via Bundle:**
  ```java
  Bundle extras = new Bundle();
  extras.putString("USER_NAME", "John Doe");
  extras.putInt("USER_ID", 21);
  extras.putIntArray("USER_SELECTIONS", new int[]{1, 2, 3, 4, 5});

  Intent intent = new Intent(this, NextActivity.class);
  intent.putExtras(extras);
  startActivity(intent);
  ```

* **Receiving via Bundle:**
  ```java
  Intent intent = getIntent();
  Bundle extras = intent.getExtras();
  String userName = extras.getString("USER_NAME");
  Integer userId = extras.getInt("USER_ID");
  ```

### Transmitting Objects (Serializable)
Java class objects (such as ArrayLists, HashMaps, or custom data classes) can be passed through bundles by implementing serialization.

* **Putting Serializable Objects:**
  ```java
  Bundle bundle = new Bundle();
  bundle.putSerializable("KEY", YOUR_OBJECT);
  intent.putExtras(bundle);
  ```

* **Retrieving Serializable Objects:**
  ```java
  Intent intent = this.getIntent();
  Bundle bundle = intent.getExtras();
  DataClass myData = (DataClass) bundle.getSerializable("MY_DATA");
  ```