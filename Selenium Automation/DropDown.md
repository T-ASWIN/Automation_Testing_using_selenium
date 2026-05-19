
***

# ✅ 1) Types of Dropdowns

## 1. Standard `<select>` Dropdown

*   Uses `<select>` and `<option>` tags
*   Selenium provides a built‑in class: **`Select`**

### ✅ Example HTML



### ✅ Selenium Code

```java
import org.openqa.selenium.support.ui.Select;

// Locate dropdown
WebElement dropdown = driver.findElement(By.id("country"));

// Create Select object
Select select = new Select(dropdown);

// Select methods
select.selectByVisibleText("India");
select.selectByValue("in");
select.selectByIndex(0);
```

***

## ✅ Get All Options from Dropdown

```java
List<WebElement> options = select.getOptions();

for (WebElement option : options) {
    System.out.println(option.getText());
}
```

👉 `getOptions()` returns all `<option>` elements.

***

# ✅ 2) Bootstrap Dropdown (Custom Dropdown)

*   Does **NOT use `<select>`**
*   Uses `<ul>`, `<li>`, `<div>`
*   You **cannot use Select class**

### ✅ Example HTML



### ✅ Selenium Code

```java
// Click dropdown
driver.findElement(By.id("dd")).click();

// Get all options
List<WebElement> options = driver.findElements(By.xpath("//ul/li"));

for (WebElement option : options) {
    if (option.getText().equals("India")) {
        option.click();
        break;
    }
}
```

***

# ✅ 3) Hidden Dropdown (Advanced Case)

👉 These dropdowns:

*   Options are **not visible in DOM initially**
*   Appear only after click / event
*   Sometimes controlled via **JavaScript events (blur, click, etc.)**

***

## 🔍 How to Handle Hidden Dropdown

### Step-by-step:

1.  Click dropdown to make options visible
2.  Inspect DOM after clicking
3.  Use XPath to collect items
4.  Click required option

***

## ✅ Example Code

```java
// Step 1: Click dropdown
WebElement dropdown = driver.findElement(By.xpath("//div[@id='dropdown']"));
dropdown.click();

// Step 2: Collect visible options
List<WebElement> options = driver.findElements(By.xpath("//div[@class='dropdown-options']//div"));

// Step 3: Select value
for (WebElement option : options) {
    if (option.getText().equals("India")) {
        option.click();
        break;
    }
}
```

***

## ✅ DevTools Trick (your note explained)

You mentioned:

> event listener → blur → remove → see options

### Explanation:

*   Some dropdowns **hide options using JavaScript (blur or CSS display:none)**
*   In Chrome DevTools:
    1.  Inspect dropdown
    2.  Go to **Event Listeners**
    3.  Find `blur` or `click` event
    4.  Temporarily disable/remove it
    5.  Options become visible in DOM

👉 This helps you:

*   Identify correct XPath
*   Understand structure

***

# ✅ Key Summary

| Type            | HTML Tag     | Selenium Approach        |
| --------------- | ------------ | ------------------------ |
| Select Dropdown | `<select>`   | `Select` class ✅         |
| Bootstrap       | `<div>/<ul>` | Click + loop ❌ Select    |
| Hidden Dropdown | Dynamic      | Click + XPath inspection |

***

# ✅ Important Tips

✔ `Select` class works **ONLY with `<select>` tag**\
✔ Always inspect DOM after clicking for dynamic dropdowns\
✔ Use **explicit wait** if elements load dynamically:

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
wait.until(ExpectedConditions.visibilityOfAllElementsLocatedBy(By.xpath("//ul/li")));
```

***
