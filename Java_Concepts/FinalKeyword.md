
***

# Final Keyword in Java

## Final Keyword

The `final` keyword is used to **restrict modification** in Java.  
It can be applied to **variables, methods, and classes**.

***

## 1️⃣ Final Variable

*   A `final` variable becomes a **constant**
*   Its value **cannot be changed once assigned**

```java
class Example {
    final int x = 10;

    void display() {
        // x = 20; ❌ Error: cannot change final variable
        System.out.println(x);
    }
}
```

✅ Value is fixed after initialization

***

## 2️⃣ Final Method

*   A `final` method **cannot be overridden** in the child class
*   Used to **prevent method modification**

```java
class Parent {
    final void show() {
        System.out.println("Final method in parent");
    }
}

class Child extends Parent {
    // void show() { } ❌ Error: cannot override final method
}
```

✅ Method can be inherited  
❌ Method cannot be overridden

***

## 3️⃣ Final Class

*   A `final` class **cannot be inherited**
*   Used to prevent class extension

```java
final class Parent {
    void display() {
        System.out.println("Final class");
    }
}

// class Child extends Parent { } ❌ Error: cannot inherit from final class
```

✅ Objects can be created  
❌ Inheritance not allowed

***

## Key Points Summary

*   `final` **variable** → makes value constant
*   `final` **method** → prevents overriding
*   `final` **class** → prevents inheritance
*   `final` keyword is used for **security and immutability**

***

## Interview Line (Very Important)

> **Final is used to restrict changes: value, method behavior, or inheritance**

***
