
***

## Exception Handling in Java

👉 **Exception handling** is a mechanism to handle **runtime errors** so that the normal flow of the program can be maintained.

> The developer generally knows **where an error *may* occur** while writing code, so exceptions are handled to avoid program termination.

***

## Types of Exceptions

Java exceptions are mainly divided into **two types**:

***

### 1️⃣ Checked Exceptions

✅ **Identified by the Java compiler at compile time**  
✅ Must be **handled using `try-catch` or declared using `throws`**

**Examples:**

*   `InterruptedException`
*   `FileNotFoundException`
*   `IOException`
*   `SQLException`

```java
FileReader fr = new FileReader("file.txt"); // Checked exception
```

📌 If not handled, the compiler gives an **error**.

***

### 2️⃣ Unchecked Exceptions

✅ **Not identified by the compiler**  
✅ Occur **at runtime**  
✅ These are subclasses of `RuntimeException`

**Examples:**

*   `ArithmeticException`
*   `NullPointerException`
*   `ArrayIndexOutOfBoundsException`
*   `NumberFormatException`

```java
int a = 10 / 0; // ArithmeticException
```

📌 Compiler does **not** force handling.

***

## Exception Handling Keywords

Java provides **5 main keywords**:
`try`, `catch`, `finally`, `throw`, `throws`

***

## `throws` Keyword ✅

*   Used to **declare an exception**
*   Used at the **method level**
*   Mainly used for **checked exceptions**
*   Does **not handle** the exception, only passes it to the calling method

### Syntax:

```java
returnType methodName() throws ExceptionName {
}
```

### Example:

```java
void readFile() throws IOException {
    FileReader fr = new FileReader("file.txt");
}
```

📌 Responsibility of handling the exception goes to the **caller method**.

***

## `throw` Keyword ✅

*   Used to **explicitly throw an exception**
*   Can be used **inside a method or block**
*   Used for **both checked and unchecked exceptions**
*   Used to create **custom exceptions**

### Syntax:

```java
throw new ExceptionName("Message");
```

### Example:

```java
void checkAge(int age) {
    if (age < 18) {
        throw new ArithmeticException("Not eligible to vote");
    }
}
```

📌 `throw` is used to **actually generate an exception**.

***

## Difference Between `throw` and `throws`

| `throw`                           | `throws`                        |
| --------------------------------- | ------------------------------- |
| Used to throw an exception        | Used to declare an exception    |
| Used inside method/body           | Used in method signature        |
| Can throw one exception at a time | Can declare multiple exceptions |
| Used at runtime                   | Used at compile time            |

***
***

## If we have `try` and `catch`, **why do we need `throws`?**

### Short Answer

✅ **`try-catch` handles the exception here**  
✅ **`throws` passes the responsibility to someone else**

So we use **`throws` when we do NOT want to handle the exception in the current method**.

***

## Think of it like responsibility 👇

### Scenario 1: You handle the problem yourself ✅ (`try-catch`)

```java
void readFile() {
    try {
        FileReader fr = new FileReader("file.txt");
    } catch (FileNotFoundException e) {
        System.out.println("File not found");
    }
}
```

✔ You **know what to do** if the error happens  
✔ Exception is **handled here itself**  
✔ Program continues smoothly

***

### Scenario 2: You don’t want to handle it ❌ (`throws`)

```java
void readFile() throws FileNotFoundException {
    FileReader fr = new FileReader("file.txt");
}
```

✔ You are saying:

> “This method **may cause an exception**.  
> Whoever calls me must handle it.”

So now the **caller** must handle it:

```java
public static void main(String[] args) {
    try {
        readFile();
    } catch (FileNotFoundException e) {
        System.out.println("Handled in main");
    }
}
```

✅ Exception is handled **at a higher level**

***

## Why not always use `try-catch`?

Because **sometimes handling the exception locally makes no sense**.

### Example:

```java
void fetchDataFromDatabase() throws SQLException {
    // database code
}
```

❓ What message should this method print?
❓ Should it close the program?
❓ Should it retry?

👉 The method **doesn’t know the business logic**  
👉 So it **delegates** the decision using `throws`

***

## When should you use WHAT?

### ✅ Use `try-catch` when:

*   You **know how to recover**
*   You can **fix or log the error**
*   You want the program to **continue here**

### ✅ Use `throws` when:

*   You **cannot handle the exception properly**
*   You want **higher-level control**
*   You are writing **library / service methods**
*   You want to avoid code duplication

***

## Very Important Point (Exam ⭐)

### Checked exceptions:

*   Must be **handled OR declared**

```java
// Two options allowed
try-catch ✅
throws ✅
```

### Unchecked exceptions:

*   No compulsion

***


