
***

# Static Keyword in Java

## Static Keyword

The `static` keyword is used to define **class-level variables and methods**.  
Static members belong to the **class**, not to objects.

***

## Rules of Static Keyword

### ✅ Static Methods

*   Static methods can access **static variables and static methods directly**
*   Static methods **cannot access non-static members directly**
*   Static methods can access non-static members **only through an object**

### ✅ Non-Static Methods

*   Non-static methods can access **both static and non-static members directly**

***

## Accessing Static Members

Static members should be accessed using the **class name**:

```java
ClassName.variable;
ClassName.method();
```

***

## Example Code

```java
class StaticExample {

    static int x = 10;   // static variable
    int y = 20;          // non-static variable

    // static method
    static void staticMethod() {
        System.out.println(x);      // ✅ allowed

        StaticExample obj = new StaticExample();
        System.out.println(obj.y);  // ✅ allowed (using object)
    }

    // non-static method
    void nonStaticMethod() {
        System.out.println(x); // ✅ allowed
        System.out.println(y); // ✅ allowed
    }

    public static void main(String[] args) {
        StaticExample.staticMethod();   // className.method()

        StaticExample obj = new StaticExample();
        obj.nonStaticMethod();
    }
}
```

***

