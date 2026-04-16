
***

# Method Overriding in Java

## Method Overriding

**Method Overriding** occurs when a **child class provides a specific implementation of a method that is already defined in its parent class**.

***

## Key Rules of Method Overriding

✅ **Possible only in multiple classes (Inheritance required)**  
✅ **Method name must be the same**  
✅ **Method signature must be the same**  
    → same method name  
    → same parameters  
✅ **Method body must be different**  
✅ Overriding happens at **runtime** (Runtime Polymorphism)

***

## Syntax

```java
class Parent {
    void show() {
        System.out.println("Parent class method");
    }
}

class Child extends Parent {
    @Override
    void show() {
        System.out.println("Child class method");
    }
}
```

***

## Important Points

*   The **return type must be the same** (or covariant)
*   Access modifier in child class should be **same or wider**
*   Static methods **cannot be overridden** (they are hidden)
*   Final methods **cannot be overridden**
*   Constructor **cannot be overridden**

***

## Example with Output

```java
class Parent {
    void display() {
        System.out.println("This is Parent");
    }
}

class Child extends Parent {
    @Override
    void display() {
        System.out.println("This is Child");
    }

    public static void main(String[] args) {
        Parent obj = new Child();
        obj.display();
    }
}
```

### Output

    This is Child

✅ Method call is decided **at runtime**

***

## Overloading vs Overriding (Quick Comparison)

| Overloading              | Overriding           |
| ------------------------ | -------------------- |
| Same class               | Parent–Child classes |
| Compile-time             | Runtime              |
| Different parameters     | Same parameters      |
| Inheritance not required | Inheritance required |

***

## Key Interview Line

> **Overriding means redefining a parent class method in the child class with the same signature but a different implementation**

***
