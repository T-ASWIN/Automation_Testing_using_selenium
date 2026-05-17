
***

# 🔹 1. Synchronization (Selenium Concept)

## ✅ What is Synchronization?

**Synchronization** means making Selenium **wait** until the web application is ready before performing actions on elements.

Modern web apps load **dynamically**, so elements may not be available immediately.

***

## ✅ Common Exceptions Related to Synchronization

### 🔸 `NoSuchElementException`

*   Element is **not present at that moment**
*   Happens due to **timing issues**
*   ✅ Solved using **waits**

### 🔸 `ElementNotFoundException`

*   Locator itself is **wrong**
*   Even if you wait, it will not be found
*   ❌ Waits **cannot fix incorrect locators**

✅ **Key Interview Point**

> Synchronization issues cause `NoSuchElementException`, not locator issues.

***

# 🔹 2. `Thread.sleep()`

```java
Thread.sleep(5000); // time in milliseconds
```

## ✅ Advantages

1.  Easy to use
2.  Simple for beginners

## ❌ Disadvantages

1.  If time is **less**, exception occurs
2.  Waits for **maximum time always**
3.  Reduces performance
4.  Needs to be written **multiple times**
5.  ❌ Not recommended in real projects

✅ **Use only for learning/demo**

***

# 🔹 3. Implicit Wait

```java
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
```

## ✅ How it Works

*   Selenium waits **up to 10 seconds**
*   If element appears earlier → proceeds immediately

## ✅ Advantages

1.  Written **only once**
2.  Applies to **all elements**
3.  No maximum wait if element is available early
4.  Easy to use

## ❌ Disadvantages

1.  If time is insufficient → exception
2.  Cannot apply **conditions**
3.  Not recommended with Explicit Wait

✅ **Best for small/simple projects**

***

# 🔹 4. Explicit Wait

> Works based on **time + condition**

## ✅ Syntax

### Declaration

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
```

### Usage

```java
wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("username")));
```

## ✅ Advantages

1.  **Condition-based**
2.  More reliable
3.  Element finding is **inclusive**
4.  Waits only until condition is true

## ❌ Disadvantages

1.  Need separate wait for each element
2.  More lines of code

***

## ✅ Common Explicit Wait Conditions

*   `alertIsPresent()`
*   `elementSelectionStateToBe()`
*   `elementToBeClickable()`
*   `elementToBeSelected()`
*   `frameToBeAvailableAndSwitchToIt()`
*   `presenceOfAllElementsLocatedBy()`
*   `presenceOfElementLocated()`
*   `textToBePresentInElement()`
*   `textToBePresentInElementLocated()`
*   `textToBePresentInElementValue()`
*   `titleIs()`
*   `titleContains()`
*   `visibilityOf()`
*   `visibilityOfAllElements()`
*   `visibilityOfAllElementsLocatedBy()`
*   `visibilityOfElementLocated()`

✅ **Most commonly used in real-time projects**

***

# 🔹 5. Fluent Wait

> Advanced form of Explicit Wait

## ✅ Features

*   Custom timeout
*   Custom polling time
*   Ignore specific exceptions

## ✅ Syntax

```java
Wait<WebDriver> wait = new FluentWait<WebDriver>(driver)
        .withTimeout(Duration.ofSeconds(20))
        .pollingEvery(Duration.ofSeconds(2))
        .ignoring(NoSuchElementException.class);

WebElement element = wait.until(driver ->
        driver.findElement(By.id("foo"))
);
```

## ✅ Advantages

*   More flexible
*   Best for **highly dynamic applications**
*   Used internally by `WebDriverWait`

✅ **Interview Tip**

> `WebDriverWait` is a child of `FluentWait`

***

# 🔹 6. Page Load Timeout

```java
driver.manage().timeouts().pageLoadTimeout(Duration.ofSeconds(5));
```

## ✅ Purpose

*   Controls **maximum page load time**
*   Throws `TimeoutException` if page does not load in time

✅ Useful for slow or unstable networks

***

# 📘 README.md (Ready to Copy)

````md
# Selenium Synchronization – README

## What is Synchronization?
Synchronization ensures Selenium waits until web elements are ready before performing actions.

---

## Common Exceptions
- NoSuchElementException → Timing issue (solved by waits)
- ElementNotFoundException → Incorrect locator

---

## Thread.sleep()
- Hard wait
- Not recommended for real projects

Pros:
- Easy

Cons:
- Always waits full time
- Reduces performance

---

## Implicit Wait
```java
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
````

Pros:

*   One-time declaration
*   Applies to all elements

Cons:

*   No conditions
*   Not flexible

***

## Explicit Wait

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("username")));
```

Pros:

*   Condition-based
*   Reliable

Cons:

*   Multiple statements needed

***

## Fluent Wait

```java
Wait<WebDriver> wait = new FluentWait<WebDriver>(driver)
        .withTimeout(Duration.ofSeconds(20))
        .pollingEvery(Duration.ofSeconds(2))
        .ignoring(NoSuchElementException.class);
```

Pros:

*   Custom polling
*   Highly flexible

***

## Page Load Timeout

```java
driver.manage().timeouts().pageLoadTimeout(Duration.ofSeconds(5));
```

Controls maximum page load time.

```

