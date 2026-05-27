

***

# ✅ What is WebElement in Selenium?

In Selenium, a **WebElement** represents a **single HTML element** present in the browser’s **DOM (Document Object Model)**.

### Examples of HTML elements:

* Button (`<button>`)
* Textbox (`<input>`)
* Link (`<a>`)
* Checkbox (`<input type="checkbox">`)
* Dropdown (`<select>`)

👉 **Every HTML element that Selenium finds becomes a WebElement object.**

***

## ✅ Simple Definition

> **WebElement is an interface in Selenium used to represent and interact with a specific element on a webpage.**

***

## ✅ How WebElement is Created (with Code)

### HTML:



### Selenium Code:

```java
WebElement userBox = driver.findElement(By.id("username"));
```

### What happens internally:

1. `driver.findElement()` searches the **DOM**
2. It locates the `<input>` element
3. Selenium returns it as a **WebElement**

***

## ✅ Why Do We Use WebElement?

Selenium **cannot directly perform actions** on HTML.

It first needs a **reference** to the element → that reference is **WebElement**.

### Common Actions:

* `click()`
* `sendKeys()`
* `getText()`
* `clear()`
* `isDisplayed()`

***

## ✅ Performing Actions Using WebElement

```java
WebElement loginBtn = driver.findElement(By.id("login"));
loginBtn.click();

WebElement name = driver.findElement(By.id("username"));
name.sendKeys("Aswin");
```

✅ Action is always performed **on WebElement**, not on WebDriver.

***

## ✅ Relationship Between WebDriver and WebElement

| WebDriver        | WebElement               |
| ---------------- | ------------------------ |
| Controls browser | Represents one element   |
| Opens URL        | Performs actions         |
| Manages windows  | Reads element properties |

### Example:

```java
WebDriver driver = new ChromeDriver();

WebElement btn = driver.findElement(By.id("submit"));
btn.click();
```

* `driver` → controls the browser
* `btn` → represents a single DOM element

***

## ✅ Common WebElement Methods (with Examples)

| Method           | Purpose          | Example                        |
| ---------------- | ---------------- | ------------------------------ |
| `click()`        | Click element    | `btn.click();`                 |
| `sendKeys()`     | Type text        | `input.sendKeys("abc");`       |
| `getText()`      | Get visible text | `label.getText();`             |
| `clear()`        | Clear textbox    | `input.clear();`               |
| `isDisplayed()`  | Visibility check | `btn.isDisplayed();`           |
| `isEnabled()`    | Enabled check    | `btn.isEnabled();`             |
| `getAttribute()` | Attribute value  | `input.getAttribute("value");` |

***

## ✅ Real‑World Analogy

Imagine:

* **Browser** → Building
* **DOM** → Rooms inside the building
* **WebDriver** → Security controller
* **WebElement** → Specific room/object

✅ WebDriver controls the building\
✅ WebElement is the **exact object** you want to interact with

***

## ✅ Short Interview Answer (Perfect)

> **WebElement in Selenium represents a single HTML element in the DOM.\
> It is used to perform actions like clicking, typing, reading text, and checking properties of webpage elements.**

***

## ✅ One‑Line Difference (Very Common Question)

> **WebDriver controls the browser, WebElement controls a specific element inside the browser.**

***

