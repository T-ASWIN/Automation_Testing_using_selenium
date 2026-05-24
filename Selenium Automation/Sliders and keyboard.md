
***

# ✅ 1. Slider (Mouse Action)

👉 Sliders are handled using **mouse actions only**

### ✅ Method:

```java
dragAndDropBy(element, x, y)
```

### ✅ Example (Slider move)

```java
Actions act = new Actions(driver);

WebElement slider = driver.findElement(By.id("slider"));

act.clickAndHold(slider)
   .moveByOffset(200, 0)   // move right
   .release()
   .perform();
```

***

✔ Important:

* Sliders move **only horizontally → y = 0**
* Prefer `clickAndHold()` instead of `dragAndDropBy()`

***

# ✅ 2. Keyboard Actions (Actions class)

You use:

* `keyDown()` → press key
* `keyUp()` → release key

***

## ✅ Example 1: Ctrl + Shift + A

```java
Actions act = new Actions(driver);

act.keyDown(Keys.CONTROL)
   .keyDown(Keys.SHIFT)
   .sendKeys("A")
   .keyUp(Keys.SHIFT)     // reverse order
   .keyUp(Keys.CONTROL)
   .perform();
```

***

### ✅ Important Rule 🔥

👉 Always release keys in **reverse order**

| Press Order  | Release Order |
| ------------ | ------------- |
| CTRL → SHIFT | SHIFT → CTRL  |

***

## ✅ Example 2: Enter Key

```java
act.keyDown(Keys.ENTER)
   .keyUp(Keys.ENTER)
   .perform();
```

👉 OR simpler:

```java
element.sendKeys(Keys.ENTER);
```

***

## ✅ Example 3: Ctrl + Click (Open link in new tab)

```java
WebElement regLink = driver.findElement(By.linkText("Register"));

Actions act = new Actions(driver);

act.keyDown(Keys.CONTROL)
   .click(regLink)
   .keyUp(Keys.CONTROL)
   .perform();
```

***

# ✅ 3. click() → WebElement vs Actions

***

## ✅ WebElement click()

```java
element.click();
```

❌ Cannot take parameters  
❌ Just simple click

***

## ✅ Actions click()

```java
act.click(element).perform();
```

✅ Can combine with keys  
✅ Can chain actions

***

## ✅ Example

```java
act.keyDown(Keys.CONTROL)
   .click(element)
   .keyUp(Keys.CONTROL)
   .perform();
```

👉 ✅ WebElement cannot do this

***

# ✅ 4. List vs Set (Multiple elements)

✔ Selenium returns:

```java
List<WebElement>
```

✅ Because:

* Order matters
* Duplicate elements possible

***

## ✅ Convert to Set (if needed)

```java
List<WebElement> elements = driver.findElements(By.tagName("a"));

Set<WebElement> unique = new HashSet<>(elements);
```

***

# ✅ 5. Opening New Tab / Window

***

## ✅ Selenium 4 Feature

```java
driver.switchTo().newWindow(WindowType.TAB);
```

***

## ✅ Example

```java
// Open new tab
driver.switchTo().newWindow(WindowType.TAB);

// Navigate to URL
driver.get("https://google.com");
```

***

## ✅ Open new Window

```java
driver.switchTo().newWindow(WindowType.WINDOW);
```

***

# ✅ Complete Example (Ctrl + Click + New Tab)

```java
WebDriver driver = new ChromeDriver();
driver.get("https://example.com");

WebElement link = driver.findElement(By.linkText("Register"));

Actions act = new Actions(driver);

// Open link in new tab using CTRL
act.keyDown(Keys.CONTROL)
   .click(link)
   .keyUp(Keys.CONTROL)
   .perform();

// OR using Selenium 4
driver.switchTo().newWindow(WindowType.TAB);
driver.get("https://google.com");
```

***

# ✅ 6. Summary (Very Important 🔥)

### ✅ Mouse Actions

* `moveToElement()`
* `dragAndDrop()`
* `clickAndHold()`

***

### ✅ Keyboard Actions

* `keyDown()`
* `keyUp()`
* Follow **reverse order rule**

***

### ✅ click() difference

| Type             | Feature                  |
| ---------------- | ------------------------ |
| WebElement click | Simple click             |
| Actions click    | Supports key combination |

***

### ✅ Windows / Tabs

| Method              | Usage      |
| ------------------- | ---------- |
| `newWindow(TAB)`    | New tab    |
| `newWindow(WINDOW)` | New window |

***

### ✅ Collections

| Method           | Returns          |
| ---------------- | ---------------- |
| `findElement()`  | Single element   |
| `findElements()` | List<WebElement> |

***

# ✅ Final Tip (Interview Gold 🔥)

👉 If interviewer asks:

**Why use Actions class?**

✅ Answer:

> Actions class is used to perform complex user interactions like mouse hover, drag and drop, keyboard operations, and composite actions which cannot be handled by simple WebElement methods.

***

✅ Now you have a **full understanding of mouse + keyboard + tab handling in Selenium**

***

