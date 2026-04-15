
***

# Inheritance in Java

## Inheritance

**Inheritance** is the mechanism by which **one class acquires the properties (variables) and behavior (methods) of another class**.

### Benefits of Inheritance

*   ✅ **Code reusability**
*   ✅ **Avoids code duplication**
*   ✅ Improves **maintainability**
*   ✅ Supports **polymorphism**

***

## Syntax

```java
class ChildClass extends ParentClass {
    // child class code
}
```

***

## Types of Inheritance in Java

### 1️⃣ Single Inheritance

One child class inherits from one parent class.

```java
class Parent {
    void show() {
        System.out.println("Parent class");
    }
}

class Child extends Parent {
}
```

***

### 2️⃣ Multilevel Inheritance

A class inherits from another class, which is also a child of another class.

```java
class A {
    void displayA() {
        System.out.println("Class A");
    }
}

class B extends A {
}

class C extends B {
}
```

***

### 3️⃣ Hierarchical Inheritance

Multiple child classes inherit from the same parent class.

```java
class Parent {
    void common() {
        System.out.println("Common method");
    }
}

class Child1 extends Parent {
}

class Child2 extends Parent {
}
```

***

### 4️⃣ Multiple Inheritance (Using Interface)

❌ Java **does not support multiple inheritance using classes**  
✅ Java supports multiple inheritance **using interfaces**

#### Important Points

*   We **cannot extend multiple classes at the same time**
*   We **can implement multiple interfaces**

```java
interface A {
    void methodA();
}

interface B {
    void methodB();
}

class C implements A, B {
    public void methodA() {
        System.out.println("Method A");
    }

    public void methodB() {
        System.out.println("Method B");
    }
}
```

***

## Object Class in Java

*   `Object` is a **predefined superclass** in Java
*   **Every class implicitly extends the `Object` class**
*   Methods like `toString()`, `equals()`, `hashCode()` come from `Object`

```java
class Sample {
    // implicitly extends Object class
}
```

***

