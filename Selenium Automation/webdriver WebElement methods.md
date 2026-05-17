
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

