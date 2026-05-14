
***

# ✅ 1. `tagName, attributes, value + (Ctrl + Shift + I)`

These are used while **inspecting elements in browser (DevTools)**:

*   **tagName** → HTML tag like `input`, `button`, `a`
*   **attributes** → properties like `id`, `name`, `class`
*   **value** → actual content inside attribute

Example:



👉 Keyboard shortcut:

*   `Ctrl + Shift + I` → Inspect

***

# ✅ 2. Basic Locators in Selenium

These are used to find elements:

### 🔹 Unique Locators

*   `id` ✅ (fast & best)
*   `name`

### 🔹 Link-specific Locators

Used only for `<a>` tag (links):

*   `linkText("Exact Text")`
*   `partialLinkText("Partial Text")`

Example:

```java
driver.findElement(By.linkText("Contact Us"));
driver.findElement(By.partialLinkText("Contact"));
```

***

### 🔹 Group/Non-Unique Locators

Used when multiple elements exist:

*   `tagName`
*   `className`

👉 Example:

```java
driver.findElements(By.tagName("input"));
driver.findElements(By.className("form-control"));
```

***

### 🔹 Advanced Locators

*   `CSS Selector`
*   `XPath`

👉 Most powerful and widely used

***

# ✅ 3. WebElement (Very Important)

### Definition:

*   `WebElement` is an **interface**
*   Represents **any HTML element**
*   Used to **interact with elements**

***

### ✅ Example:

```java
WebElement searchBox = driver.findElement(By.name("q"));
searchBox.sendKeys("Selenium");
```

***

### ✅ Common Actions:

| Method          | Purpose             |
| --------------- | ------------------- |
| `sendKeys()`    | Type text           |
| `click()`       | Click               |
| `getText()`     | Get visible text    |
| `clear()`       | Clear text          |
| `isDisplayed()` | Visible or not      |
| `isEnabled()`   | Enabled or disabled |

***

# ✅ 4. `isDisplayed()`

✔ Used to check if element is visible

Example:

```java
WebElement img = driver.findElement(By.id("logo"));
System.out.println(img.isDisplayed());
```

👉 Mainly used for:

*   Images
*   Buttons
*   Text visibility

***

# ✅ 5. Multiple Class Names

HTML supports multiple classes:



✔ Two classes:

*   `search-box-text`
*   `ui-autocomplete-input`

👉 Important:

*   `By.className()` accepts **only ONE class**

❌ Wrong:

```java
By.className("search-box-text ui-autocomplete-input");
```

✅ Correct:

```java
By.className("search-box-text");
```

OR use:

```java
By.cssSelector(".search-box-text.ui-autocomplete-input");
```

***

# ✅ 6. Link Locator Examples

```java
By.partialLinkText("lets");
By.linkText("Contact Us");
```

✔ Used only for `<a>` tags

***

# ✅ 7. `findElement` vs `findElements`

⚠ Your note has a small mistake, let’s correct:

### ✅ `findElement()`

*   Returns **single WebElement**
*   If not found → ❌ `NoSuchElementException`

```java
WebElement e = driver.findElement(By.id("user"));
```

***

### ✅ `findElements()`

*   Returns **List<WebElement>**
*   If not found → ✅ returns **empty list (NOT error)**

```java
List<WebElement> list = driver.findElements(By.tagName("input"));
```

***

# ✅ 8. Exception Handling

✔ Correct idea:

*   If element NOT found:

```java
driver.findElement(...)
```

👉 throws:
❌ `NoSuchElementException`

***

# ✅ 9. Summary (Simple)

*   Locators → Used to find elements
*   WebElement → Represents element
*   `findElement()` → single element
*   `findElements()` → multiple elements
*   Use `id` first → best practice
*   Use XPath / CSS → if basic locators fail

***

# ✅ Final Tip (Important for Interview)

👉 Locator priority order:

1.  `id`
2.  `name`
3.  `className`
4.  `linkText`
5.  `CSS Selector`
6.  `XPath`

***

