# Module 6: Android User Interface - Comprehensive Context File

## 1. Objectives & Overview

* **Target Learning Outcomes:**

  * Understand the concepts of `View` and `ViewGroup`.

  * Declare UI elements in XML or instantiate them at runtime.

  * Design user interfaces using multiple layouts and view hierarchies.

  * Apply UI controls (widgets) and input elements.

  * Apply event listeners and handle user interactions.

* **Core Definitions:**

  * **`View`:** Usually called a "widget"; draws something the user can see and interact with on the screen (e.g., `TextView`, `Button`, `EditText`).

  * **`ViewGroup`:** Usually called a "layout"; an invisible container that defines the layout structure for `View` and other `ViewGroup` objects.

## 2. Declaring Layouts & Views

Views and ViewGroups can be declared in two ways:

1. **Declaratively in XML:** Defined in XML resource files under `res/layout/filename.xml` and loaded in Java/Kotlin via `setContentView(R.layout.filename)`.

2. **Programmatically at Runtime:** Instantiated and structured directly in code (e.g., inside `onCreate()`).

### Example: Declaring Layout in XML (`activity_main.xml`)

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/fstTxt"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Enter Name" />

    <EditText
        android:id="@+id/name"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10" />

    <Button
        android:id="@+id/getName"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Get Name" />

</LinearLayout>
```

### Example: Instantiating Layout Elements at Runtime

```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        
        TextView textView1 = new TextView(this);
        textView1.setText("Name:");

        EditText editText1 = new EditText(this);
        editText1.setText("Enter Name");

        Button button1 = new Button(this);
        button1.setText("Add Name");

        LinearLayout linearLayout = new LinearLayout(this);
        linearLayout.addView(textView1);
        linearLayout.addView(editText1);
        linearLayout.addView(button1);

        setContentView(linearLayout);
    }
}
```

## 3. Major Layout Types

* **Linear Layout (`LinearLayout`):** Renders child views sequentially in either a horizontal or vertical direction based on `android:orientation`. Supports `layout_weight` to distribute screen space proportionally.

* **Relative Layout (`RelativeLayout`):** Positions child views relative to each other or to the parent container (e.g., `layout_below`, `layout_toRightOf`, `layout_centerInParent`), keeping view hierarchies flat for better performance.

* **Frame Layout (`FrameLayout`):** Designed to display a single item or stack multiple child views on top of each other (with the most recently added view on top). Controlled using `layout_gravity`.

* **Table Layout (`TableLayout`):** Positions child views into rows (`TableRow`) and columns, behaving similarly to HTML tables.

* **WebView (`WebView`):** Embedded browser component used to display static HTML content or remote web pages.

* **ListView (`ListView`):** Displays a scrollable list of items in multiple rows, populated dynamically using adapters (`ArrayAdapter`, `CursorAdapter`, `SimpleAdapter`, `BaseAdapter`).

* **GridView (`GridView`):** Displays items in a two-dimensional, scrollable grid, populated using adapters.

## 4. Common UI Controls (Widgets)

* **`TextView`:** Displays text to the user.

* **`EditText`:** Subclass of `TextView` with rich text editing capabilities.

* **`Button` & `ImageButton`:** Clickable push-buttons with text or images.

* **`CheckBox` & `ToggleButton`:** Selectable options (checkboxes for multiple selections, toggle buttons for on/off states).

* **`RadioButton` & `RadioGroup`:** Mutually exclusive option selectors.

* **`ProgressBar`:** Visual feedback for ongoing tasks.

* **`Spinner`:** Drop-down list for selecting a single value.

## 5. Event Handling & Listeners

Event listeners are interfaces containing callback methods triggered by user interactions.

### Common Event Listeners & Handlers

* **`OnClickListener` (`onClick()`):** Triggered when a widget is clicked, touched, or focused.

* **`OnLongClickListener` (`onLongClick()`):** Triggered when a widget is held/touched for 1+ seconds.

* **`OnFocusChangeListener` (`onFocusChange()`):** Triggered when a widget gains or loses focus.

* **`OnTouchListener` (`onTouch()`):** Triggered on touch gestures or motion events.

### Implementation Example (Anonymous Class & Activity Registration)

```java
public class ExampleActivity extends Activity {
    private View.OnClickListener corkyListener = new View.OnClickListener() {
        public void onClick(View v) {
            // Do something when button is clicked
        }
    };

    protected void onCreate(Bundle savedValues) {
        super.onCreate(savedValues);
        setContentView(R.layout.activity_main);

        Button button = (Button) findViewById(R.id.corky);
        button.setOnClickListener(corkyListener);
    }
}
```