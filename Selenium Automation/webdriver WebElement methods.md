
👉 **<https://testautomationpractice.blogspot.com>**


***

# ✅ Selenium WebDriver Methods – Explained

***

## 1️⃣ GET METHODS

👉 **Accessed through `WebDriver` instance**

### ✅ Purpose

Used to **get information from the browser/page**

***

### 🔹 Methods

```java
driver.get("https://testautomationpractice.blogspot.com/");
```

*   Opens the application URL in the browser

```java
driver.getTitle();
```

*   Returns **page title**

```java
driver.getCurrentUrl();
```

*   Returns **current page URL**

```java
driver.getPageSource();
```

*   Returns **HTML source code** of the page

```java
driver.getWindowHandle();
```

*   Returns **single browser window ID**

```java
driver.getWindowHandles();
```

*   Returns **all open browser window IDs**

***

### ✅ Example (TestAutomationPractice)

```java
WebDriver driver = new EdgeDriver();
driver.get("https://testautomationpractice.blogspot.com/");

System.out.println(driver.getTitle());
System.out.println(driver.getCurrentUrl());
System.out.println(driver.getWindowHandle());
```

***

## 2️⃣ CONDITIONAL METHODS

👉 **Accessed through `WebElement`**  
👉 **Return boolean (`true / false`)**

***

### ✅ Purpose

Used to **verify element state**

***

### 🔹 Methods

```java
isDisplayed()  // element visible or not
isEnabled()   // element enabled or disabled
isSelected()  // checkbox / radio selected or not
```

***

### ✅ Example (TestAutomationPractice)

```java
WebElement searchBox = driver.findElement(By.id("Wikipedia1_wikipedia-search-input"));

System.out.println(searchBox.isDisplayed()); // true
System.out.println(searchBox.isEnabled());   // true
```

Checkbox example:

```java
WebElement maleRadio = driver.findElement(By.id("male"));

System.out.println(maleRadio.isSelected());
maleRadio.click();
System.out.println(maleRadio.isSelected());
```

***

## 3️⃣ BROWSER METHODS

👉 **Accessed through `WebDriver`**

***

### 🔹 Methods

```java
driver.close();
```

*   Closes **current browser window**

```java
driver.quit();
```

*   Closes **all browser windows**
*   Ends WebDriver session

***

### ✅ Example

```java
driver.close(); // single window
// OR
driver.quit();  // all windows
```

✅ **Interview Tip:**

> `quit()` is preferred in real-time projects

***

## 4️⃣ NAVIGATIONAL METHODS

👉 Used to **navigate between pages**

***

### 🔹 Methods

```java
driver.navigate().to("url");
driver.navigate().back();
driver.navigate().forward();
driver.navigate().refresh();
```

***

### ✅ Example (TestAutomationPractice)

```java
driver.navigate().to("https://testautomationpractice.blogspot.com/");
driver.navigate().refresh();
driver.navigate().back();
driver.navigate().forward();
```

***


### Short answer

✅ **Both `get()` and `navigate().to()` are used to open URLs**  
❌ `navigate()` is **not limited only to `.to()`**

***

## ✅ Difference between `get()` and `navigate().to()`

### 1️⃣ `driver.get(url)`

**Purpose**

* Open a URL
* Waits until the **entire page is fully loaded**

**Key points**

* Simpler, most commonly used
* Does **not** keep browser history control

**Example**

```java
driver.get("https://google.com");
```

***

### 2️⃣ `driver.navigate().to(url)`

**Purpose**

* Also opens a URL
* Part of **browser navigation**

**Key points**

* Works like typing a URL in browser address bar
* Does **not always wait** completely like `get()`
* Allows **back, forward, refresh**

**Example**

```java
driver.navigate().to("https://google.com");
```

***

## ✅ Navigation commands (important)

`navigate()` gives you **browser-like controls**:

```java
driver.navigate().to("https://site1.com");
driver.navigate().back();
driver.navigate().forward();
driver.navigate().refresh();
```

So ❗  
👉 We don't use `navigate()` *only* for `.to()`  
👉 We use it when **browser history matters**

***

## ✅ Interview-friendly comparison

| Aspect              | get() | navigate().to() |
| ------------------- | ----- | --------------- |
| Opens URL           | ✅     | ✅               |
| Waits for full load | ✅     | ⚠️ Not always   |
| Browser history     | ❌     | ✅               |
| Back / Forward      | ❌     | ✅               |
| Simplicity          | ✅     | ⚠️              |

***

## ✅ When to use what?

### Use `get()` when:

* Opening a page for the first time
* Login pages
* Simple flows

### Use `navigate()` when:

* Testing back/forward behavior
* Multi-page flows
* Browser-like navigation testing

***

