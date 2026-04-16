Super
   -->super keyword will be used to invoke the immedite parent class variable
   -->super keyword will be used to invoke the immedite parent class method
   -->super keyword will be used to invoke the immedite parent class constructor



***

## ✅ Where can `super` be used?

### 1️⃣ **Inside a constructor**

👉 To call the **parent class constructor**

```java
class Parent {
    Parent(int x) {
        System.out.println(x);
    }
}

class Child extends Parent {
    Child() {
        super(10);   // ✅ allowed (constructor)
    }
}
```

🔹 Rules:

*   `super()` **must be inside a constructor**
*   It must be the **first statement**

***

### 2️⃣ **Inside an instance method**

👉 To access **parent methods or variables**

```java
class Parent {
    int x = 10;

    void show() {
        System.out.println("Parent show");
    }
}

class Child extends Parent {
    int x = 20;

    void display() {
        System.out.println(super.x); // ✅ parent variable
        super.show();                // ✅ parent method
    }
}
```

***

## ❌ Where `super` CANNOT be used

🚫 Directly inside the class body  
🚫 Inside static methods  
🚫 Outside inheritance

```java
class Child extends Parent {
    super.show();   // ❌ INVALID
}
```

```java
static void test() {
    super.show();   // ❌ INVALID
}
```

***

## ✅ Simple rule to remember (Very Important)

> 🔹 Use `super()` → **only in constructors**  
> 🔹 Use `super.variable` or `super.method()` → **inside instance methods**

***

