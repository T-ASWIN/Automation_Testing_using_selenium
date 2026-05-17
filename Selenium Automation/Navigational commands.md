
***

# ✅ Navigational Commands in Selenium WebDriver

Navigational commands are used to **move between web pages** and **control browser navigation**.

***

## 🔹 1. Navigational Methods

### ✅ `navigate().to(url)`

```java
driver.navigate().to("https://testautomationpractice.blogspot.com/");
```

✅ Opens the URL  
✅ Accepts:

*   **String URL**
*   **URL object**

```java
URL url = new URL("https://testautomationpractice.blogspot.com/");
driver.navigate().to(url);
```

***

### ✅ `navigate().back()`

```java
driver.navigate().back();
```

*   Moves to **previous page**
*   Same as browser **Back button**

***

### ✅ `navigate().forward()`

```java
driver.navigate().forward();
```

*   Moves to **next page**
*   Same as browser **Forward button**

***

### ✅ `navigate().refresh()`

```java
driver.navigate().refresh();
```

*   Reloads the current page

***

## 🔹 2. Difference: `driver.get()` vs `driver.navigate().to()`

### ✅ `driver.get()`

```java
driver.get("https://testautomationpractice.blogspot.com/");
```

✔ Accepts **String URL only**  
✔ Waits until page is fully loaded  
✔ Most commonly used to launch application

***

### ✅ `driver.navigate().to()`

```java
driver.navigate().to("https://testautomationpractice.blogspot.com/");
```

✔ Accepts:

*   String URL
*   URL object  
    ✔ Supports **back, forward, refresh**

***

### ✅ Interview Difference Table

| Feature            | `get()` | `navigate().to()` |
| ------------------ | ------- | ----------------- |
| Accepts String     | ✅       | ✅                 |
| Accepts URL object | ❌       | ✅                 |
| Navigation support | ❌       | ✅                 |
| Page load wait     | ✅       | ✅                 |

✅ **Conclusion:**

> `get()` is used for launching the app, `navigate()` is used for browser navigation.

***

## 🔹 3. Window Handling Methods

Used when **multiple browser windows or tabs** are opened.

***

### ✅ `getWindowHandle()`

```java
String windowID = driver.getWindowHandle();
```

✔ Returns **unique ID of current window**  
✔ Used to identify **parent window**

***

### ✅ `getWindowHandles()`

```java
Set<String> windowIDs = driver.getWindowHandles();
```

✔ Returns **IDs of all open windows**  
✔ Stored as `Set<String>`

***

## 🔹 4. Switching Between Windows

### ✅ `driver.switchTo().window(windowID)`

```java
driver.switchTo().window(windowID);
```

✔ Switches control to the specified window  
✔ Mandatory for working with child windows/tabs

***

## ✅ Example: Window Handling (TestAutomationPractice)

```java
WebDriver driver = new EdgeDriver();
driver.get("https://testautomationpractice.blogspot.com/");

String parentWindow = driver.getWindowHandle();

// Assume clicking opens new tab
driver.findElement(By.id("Wikipedia1_wikipedia-search-button")).click();

Set<String> allWindows = driver.getWindowHandles();

for (String win : allWindows) {
    if (!win.equals(parentWindow)) {
        driver.switchTo().window(win);
        System.out.println(driver.getTitle());
    }
}

// Switch back to parent window
driver.switchTo().window(parentWindow);
```

***
