````markdown
# Wrapper Class

## Definition
- **Wrapper Classes** are part of Java’s **derived data types**
- They are used to **convert primitive data types into objects** and **objects back into primitive data types**

---

## Why Wrapper Class?
- In **Collections**, we can store data **only in the form of objects**
- Primitive data types (`int`, `float`, `char`, etc.) **cannot be stored directly**
- To solve this, Java provides **Wrapper Classes** (object classes)

---

## Primitive to Object Conversion
- Wrapper class converts **primitive → object**
- Example:
```java
int a = 10;
Integer obj = a;  // Autoboxing
````

***

## Object to Primitive Conversion

*   Wrapper class converts **object → primitive**
*   Example:

```java
Integer obj = 20;
int b = obj;  // Unboxing
```

***

## Autoboxing

*   **Autoboxing**: Automatically converts a **primitive** into its corresponding **wrapper object**
*   Example:

```java
int x = 5;
Integer y = x;
```

***

## Unboxing

*   **Unboxing**: Automatically converts a **wrapper object** into a **primitive**
*   Example:

```java
Integer x = 15;
int y = x;
```

***

## Common Wrapper Classes

| Primitive | Wrapper Class |
| --------- | ------------- |
| int       | Integer       |
| float     | Float         |
| double    | Double        |
| char      | Character     |
| boolean   | Boolean       |
| byte      | Byte          |
| short     | Short         |
| long      | Long          |

***

