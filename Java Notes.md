# Java Notes


### Basics

* Strongly typed, statically typed.
* Everything resides in a class.
* Entry point: `public static void main(String[] args)`
	* The class in which this resides can be named anything, you just need to set it in the Manifest or when running `java MyMainClass`

---

### OOP Features

* Classes: `class MyClass { }`
* Inheritance:
	* `class Child extends Parent`
* Interfaces: Similar to abstract base classes.
	* `public class Duck implements Flyable, Swimmable` for implementing the interfaces 
* Encapsulation: `private`, `protected`, `public`
	* `protected` objects are private but can still be accessed by the same package & subclasses
* Polymorphism: Method overloading/overriding.
* No multiple *inheritance*
	* You can *inherit* one class and implement any number of interfaces.
	* `public class Duck extends Animal implements Flyable, Swimmable` inherits `Animal` class and implements `Flyable` & `Swimmable` interfaces.
`

---

### Primitive Types

```java
int, float, double, char, boolean, long, byte, short
```

* Primitive types **are not objects** (unlike Python).
* Objects are different: `Integer`, `Double`, etc.
* Use `.equals()` for object comparison, not `==`.

---

### Casting

```java
int a = (int) 3.14;          // explicit (narrowing)
double b = 5;                // implicit (widening)
Animal a = new Dog();        // upcasting
Dog d = (Dog) a;             // downcasting
```

---

### Collections

```java
ArrayList<String> list = new ArrayList<>(); // effectively a vector
list.add("hello");           // append
list.get(0);                 // index (read)
list.set(0, "world");        // index (write)
list.remove(0);              // remove by index
list.size();                 // length
list.contains("foo");        // membership check
list.clear();                // empty the list
```


```java
HashMap<String, Integer> map = new HashMap<>();

map.put("key", 42);          // insert/update
map.get("key");              // retrieve (null if not found)
map.containsKey("key");      // membership check
map.remove("key");           // delete
map.size();                  // number of entries
map.clear();                 // empty the map

```

---
### File I/O

```java
import java.io.*;

// Reading
BufferedReader br = new BufferedReader(new FileReader("file.txt"));
String line = br.readLine();
br.close();

// Writing
BufferedWriter bw = new BufferedWriter(new FileWriter("file.txt"));
bw.write("Hello");
bw.close();
```

---

### Error Handling

```java
try {
    // risky code
} catch (IOException e) {
    // handle it
} finally {
    // always runs
}
```

### Interfaces 

```java
public interface Logger {
    void log(String message);  // abstract method

    default void logError(String message) { // already implemented
        log("ERROR: " + message);
    }
}
```

### Annotations

* `@Override` — indicates method overrides superclass/interface method
* `@Deprecated` — marks elements as obsolete
* `@SuppressWarnings` — disables specified compiler warnings
* `@FunctionalInterface` — marks interface as functional (single abstract method)
* `@SafeVarargs` — suppresses unchecked warnings on varargs with generics
* `@Retention` — defines annotation lifespan (SOURCE, CLASS, RUNTIME)
* `@Target` — restricts where annotation can be applied (method, field, class, etc.)
* `@Documented` — includes annotation in Javadoc
* `@Inherited` — allows subclass to inherit annotation from superclass


### Class Constants

```java
public class Constants {
    public static final double PI = 3.14159;
    public static final int MAX_VALUE = 100;
}
```

### Keywords

- `static` : Member belongs to the class itself, not to any instance. Accessible without creating an object.
	- You can reference with `ClassName.staticVariable` (the same goes for functions)
- `final`: Analogous to `const`


### `this`

Analogous to `self` in Python, expect it is inferred, not passed.

```java
public void setName(String name) {
    this.name = name;  // 'this' refers to the current object
}
```

You'll get a compile-time error if you try to use `this` in a static function

*Note:* You don't generally need to use `this` to access class attributes; however, like in the example above, if a parameter name overlaps with a class attribute name, you can use `this` to disambiguate the two. Otherwise, you could just use:

```java
public void setName(String user_name) {
    name = user_name;
}

```

### Switch Statements

```java
switch (variable) {
    case value1:
        // statements
        break;
    case value2:
        // statements
        break;
    default:
        // statements
}
```

### Loops

```java
// for loop
for (int i = 0; i < 10; i++) {
    // body
}

// enhanced for loop (for-each)
for (Type item : collection) {
    // body
}

// while loop
while (condition) {
    // body
}

// do-while loop
do {
    // body
} while (condition);

```

* `while` checks the condition **before** executing the loop body (zero or more iterations).
* `do-while` executes the loop body **once before** checking the condition (one or more iterations).


### Imports

If a class has a unique name, it can be imported as:

```java
import package.Date;
```

However, if necessary, it can be imported with a fully qualified name starting at `com`, which usually sits at `src/com/example/project/SomeClass.java`. The fully qualified name for `SomeClass` would be:

```java
import com.example.project.ClassName;
```

You can ignore the import entirely (though not recommended) and use the fully qualified name directly in the code:

```java
com.example.project.ClassName my_inst = new com.example.project.ClassName();
```

There is **one class per file**, and the filename will match that classname. Additionally, each file starts with `package <qualified_name>;` (not including the class name); e.g. `package com.my_project.api;` for `src/com/my_project/api/RestApi.java`


### Constructors

Constructors are methods that are named the same as the class. You can overload these as many times as you want:


```java
public class User {
    private String name;

    // Constructor
    public User(String name) {
        this.name = name;
    }
}
```

### Getters & Setters

You *can* set public attributes like you do in Python, i.e.

```java
user.name = "Jason";
```

But this is generally considered **poor practice**. You should set the attributes to be private and expose certain setters/getters to interface with them:

```java
user.setName("Alice");
String n = user.getName();
```

### String Formatting

| Specifier | Type              |
| --------- | ----------------- |
| `%s`      | String            |
| `%d`      | Integer (decimal) |
| `%f`      | Floating point    |
| `%x`      | Integer (hex)     |
| `%o`      | Integer (octal)   |
| `%c`      | Character         |
| `%b`      | Boolean           |
| `%%`      | Literal `%`       |
You can use these like:

```java
String.format("%s is %d years old", "Alice", 30);
String.format("%.2f", 3.14159); // 3.14
```

You can use `%.2f` for `2` digits of precision when showing floats. ofc this works with other numbers too.