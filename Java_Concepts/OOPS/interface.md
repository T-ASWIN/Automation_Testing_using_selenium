
***

# Interface in Java

## Interface

An **interface** in Java is used to achieve **abstraction and multiple inheritance**.  
It defines **what a class should do**, not **how it should do it**.

***

## Key Points of Interface

1.  ✅ An interface is a **blueprint of a class**
2.  ✅ Interfaces contain **public, static, and final variables by default**
3.  ✅ Interfaces contain **abstract methods**
    *   From **Java 8 onwards**, interfaces can also have:
        *   `default` methods
        *   `static` methods
4.  ✅ An **abstract method** has only the **method signature**, not the body (unimplemented method)
5.  ✅ All methods in an interface are **public by default**
6.  ✅ Interface supports **multiple inheritance**
7.  ✅ An interface is defined using the **`interface` keyword**
8.  ✅
    *   A class **extends** another class
    *   An interface **extends** another interface
    *   A class **implements** an interface
9.  ✅ We can create an **interface reference**, but **we cannot instantiate an interface**

***

## Syntax

```java
interface InterfaceName {
    // variables
    // abstract methods
}
```

***

## Example

```java
interface Vehicle {

    // public static final variable (by default)
    int speed = 60;

    // abstract method (by default public abstract)
    void start();

    // default method (Java 8+)
    default void stop() {
        System.out.println("Vehicle stopped");
    }

    // static method (Java 8+)
    static void info() {
        System.out.println("Vehicle Interface");
    }
}

class Car implements Vehicle {

    public void start() {
        System.out.println("Car started");
    }

    public static void main(String[] args) {

        Vehicle obj = new Car(); // interface reference
        obj.start();
        obj.stop();

        Vehicle.info(); // static method call
    }
}
```

***

## Important Notes

*   Interface variables are **always constant**
*   Interface methods are **always public**
*   An interface **cannot have constructors**
*   An interface **cannot be instantiated**

***

