
***

# ✅ 1. Alerts in Selenium

An **alert** is a small popup box that appears on the browser.  
Types:

*   Simple Alert (OK button)
*   Confirmation Alert (OK + Cancel)
*   Prompt Alert (input field)

### 🔹 Basic Alert Handling Methods

```java
driver.switchTo().alert().accept();   // Click OK
driver.switchTo().alert().dismiss();  // Click Cancel
driver.switchTo().alert().getText();  // Get alert message
driver.switchTo().alert().sendKeys("text");  // Enter text in prompt alert
```

***

## ✅ Capturing Alert WITHOUT `switchTo().alert()`

Normally, you must use `switchTo().alert()`.  
But before interacting, you can **wait for alert using Explicit Wait**.

### 🔹 Using Explicit Wait (Best Practice)

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));

// Wait until alert is present
Alert alert = wait.until(ExpectedConditions.alertIsPresent());

// Now perform actions
System.out.println(alert.getText());
alert.accept();
```

✅ **Why this is useful:**

*   Prevents `NoAlertPresentException`
*   Ensures alert appears before interacting
*   Cleaner & safer than direct switch

👉 Note:
You are **still using Alert internally**, but avoiding immediate `switchTo()` call without validation.

***

## ✅ Can this be used for Cookies?

Not exactly the same.

*   Alerts = browser popups handled via `Alert`
*   Cookies = handled using:

```java
driver.manage().getCookies();
driver.manage().addCookie(cookie);
driver.manage().deleteCookieNamed("name");
```

👉 Explicit wait is **not directly used for cookies**, but you can wait for elements like cookie popups.

***

# ✅ 2. Frames in Selenium

A **frame (iframe)** is like a webpage inside another webpage.

👉 Selenium cannot directly interact with elements inside a frame unless you switch into it.

***

## 🔹 Ways to Switch to Frame

```java
driver.switchTo().frame(name);      // Using frame name
driver.switchTo().frame(id);        // Using frame id
driver.switchTo().frame(index);     // Using index (0,1,2…)
driver.switchTo().frame(WebElement); // Using WebElement
```

***

## 🔹 Switch Back to Main Page

```java
driver.switchTo().defaultContent();
```

✅ Moves control back to the main HTML page.

***

## 🔹 Nested Frames (Inner Frames)

Sometimes frames are inside another frame.

### Example:

```java
driver.switchTo().frame("parentFrame");   // First go to parent frame
driver.switchTo().frame("childFrame");    // Then go to child frame

// Perform actions

driver.switchTo().defaultContent(); // Back to main page
```

👉 You must switch **step by step**.

***

## ✅ Important Points

### 🔹 Alerts

*   Cannot inspect via DOM
*   Must use `alert()` handling
*   Use explicit wait for stability

### 🔹 Frames

*   Part of DOM
*   Must switch context before interacting
*   Always switch back after work

***

## ✅ Quick Summary

| Feature         | Key Method                            |
| --------------- | ------------------------------------- |
| Accept alert    | `alert().accept()`                    |
| Dismiss alert   | `alert().dismiss()`                   |
| Get alert text  | `alert().getText()`                   |
| Wait for alert  | `ExpectedConditions.alertIsPresent()` |
| Switch to frame | `driver.switchTo().frame()`           |
| Exit frame      | `driver.switchTo().defaultContent()`  |

***

