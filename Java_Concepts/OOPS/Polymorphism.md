
***

# Polymorphism in Java

## Polymorphism

**Polymorphism** means **many forms**.  
In Java, it allows a method, object, or class to behave differently based on the context.

***

## Method Overloading

**Method Overloading** is a type of **compile-time polymorphism**.

### Definition

Method overloading means **using the same method name with different parameters** in the same class.

***

### Rules for Method Overloading

✅ **Method name must be the same**  
✅ **Parameters must be different**, which can be:

*   Different **number of parameters**
*   Different **data types**
*   Different **order of parameters** (only if data types are different)

⚠️ **Return type alone cannot be different**  
Changing only the return type does **NOT** qualify as method overloading.

✅ **The `main` method can also be overloaded**

***

### Example

```java
class Example {

    void add(int a, int b) {
        System.out.println(a + b);
    }

    void add(int a, int b, int c) {
        System.out.println(a + b + c);
    }

    double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        Example obj = new Example();
        obj.add(10, 20);
        obj.add(10, 20, 30);
        System.out.println(obj.add(5.5, 4.5));
    }
}
```

***

### Key Points Summary

*   Polymorphism = **Many forms**
*   Method overloading happens **within the same class**
*   Overloading improves **code readability and reusability**
*   Java decides which method to call **at compile time**

***
