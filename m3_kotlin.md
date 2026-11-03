# Module 3: Introduction to Kotlin - Comprehensive Context File

## 1. Objectives & Overview

* **Target Learning Outcomes:**
  * Understand what Kotlin is and its primary uses.
  * Write code using Kotlin fundamentals and OOP principles.
  * Compare Kotlin with Java.
  * Migrate Java code/files to Kotlin in Android Studio.

* **Core Definition:** Kotlin is a modern, trending, concise, and safe programming language released in 2006 (stable release 2016) by JetBrains. It is 100% compatible with Java, cross-platform (Windows, Mac, Linux, Raspberry Pi), and widely used for Android applications, web development, server-side apps, and data science.

---

## 2. Kotlin Code Examples & Fundamentals

### Basic Syntax & Input/Output
```kotlin
import java.util.Scanner

fun main(args: Array<String>) {
    val reader = Scanner(System.`in`)
    print("Enter a number: ")
    var integer: Int = reader.nextInt()
    println("You entered: $integer")
}
```

### Variables (`val` vs `var`)
* **`val`**: Immutable reference (cannot be modified after initialization, similar to `final`).
* **`var`**: Mutable reference (can be reassigned).
* **Type Inference**: Kotlin automatically determines variable data types.

```kotlin
fun main() {
    var mutable = "Hello World" // Can be changed
    val immutable = 12          // Cannot be changed
    mutable = "Hi there"
    println(mutable)
    println(immutable)
}
```

### Nullability & Initialization
```kotlin
fun main() {
    lateinit var str1: String
    var str2: String? = null
    str1 = "late init"
    println(str1)
    println(str2)
}
```

---

## 3. Control Flow

### If-Else Statements & Expressions
```kotlin
val time = 20
val greeting = if (time < 18) {
    "Good day."
} else {
    "Good evening."
}
println(greeting)
```

### When Expression
```kotlin
val day = 4
val result = when (day) {
    1 -> "Monday"
    2 -> "Tuesday"
    3 -> "Wednesday"
    4 -> "Thursday"
    5 -> "Friday"
    6 -> "Saturday"
    7 -> "Sunday"
    else -> "Invalid day."
}
println(result) // Outputs "Thursday"
```

### Loops
```kotlin
// Array loop
val nums = arrayOf(1, 5, 10, 15, 20)
for (x in nums) {
    println(x)
}

// Range loop
for (n in 5..15) {
    println(n)
}
```

---

## 4. Object-Oriented Programming (OOP) in Kotlin

### Classes and Objects
```kotlin
class Car {
    var brand = ""
    var model = ""
    var year = 0
}

fun main() {
    val c1 = Car()
    c1.brand = "Ford"
    c1.model = "Mustang"
    c1.year = 1969
    println(c1.brand)
    println(c1.model)
    println(c1.year)
}
```

### Primary Constructors & Init Blocks
```kotlin
class Person (val _name: String) {
    var name: String
    init {
        this.name = _name
        println("Name = $name")
    }
}

fun main(args: Array<String>) {
    val person = Person("Abe")
}
```

### Secondary Constructors
```kotlin
class Add {
    constructor(a: Int, b: Int) {
        val c = a + b
        println("Sum = $c")
    }
    constructor(a: Int, b: Int, c: Int) {
        val d = a + b + c
        println("Sum = $d")
    }
}
```

### Inheritance
```kotlin
open class MyParentClass {
    val x = 5
}

class MyChildClass : MyParentClass() {
    fun myFunction() {
        println(x) // Inherited from superclass
    }
}
```

---

## 5. Kotlin vs Java Comparison

| Feature | Kotlin | Java |
| :--- | :--- | :--- |
| **Extension Functions** | Available natively | Requires utility classes |
| **Null Safety** | Built into type system (`?`) | Prone to `NullPointerException` |
| **Static Members** | Uses `companion object` | Uses `static` keyword |
| **String Templates** | Supported directly (`$var`) | Requires concatenation (`+`) |
| **Checked Exceptions** | Removed entirely | Mandatory handling (`try-catch`/`throws`) |
| **Constructors** | Primary and secondary constructors | Constructor methods |

---

## 6. Kotlin in Android & Code Conversion

### Android Kotlin Example (`MainActivity.kt`)
```kotlin
lateinit var textView: TextView

override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)
    
    textView = findViewById(R.id.text_view)
    textView.text = "New Text"
}
```

### Converting Java Code to Kotlin in Android Studio
1. **Method 1 (Complete File Conversion):** Right-click a Java file in the project structure, select **Convert Java File to Kotlin File** (or shortcut `Ctrl+Alt+Shift+K`), and grant permission to configure Kotlin with Gradle.
2. **Method 2 (Paste Conversion):** Create a new `.kt` file. When prompted, configure Kotlin in all modules via Gradle, then paste Java code directly into the Kotlin file for automatic syntax conversion.