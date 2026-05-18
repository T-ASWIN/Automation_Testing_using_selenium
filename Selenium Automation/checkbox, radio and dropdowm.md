
***

# ✅ 1. CHECK BOXES

### 🔹 What is a checkbox?

*   Allows **multiple selections**
*   HTML tag: `<input type="checkbox">`

### ✅ Example Site

<https://testautomationpractice.blogspot.com/>

***

## ✅ Select a Single Checkbox

```java
driver.findElement(By.id("sunday")).click();
```

✅ Clicks the **Sunday** checkbox

***

## ✅ Count All Checkboxes

```java
List<WebElement> checkboxes =
        driver.findElements(By.xpath("//input[@type='checkbox']"));

System.out.println("Total checkboxes: " + checkboxes.size());
```

***

## ✅ Select ALL Checkboxes

```java
for (WebElement cb : checkboxes) {
    if (!cb.isSelected()) {
        cb.click();
    }
}
```

***

## ✅ Check If Checkbox Is Selected

```java
boolean status = driver.findElement(By.id("sunday")).isSelected();
System.out.println("Sunday selected: " + status);
```

***

# ✅ 2. DROPDOWNS

There are **3 TYPES of dropdowns** 👇

***

# ✅ TYPE 1: Dropdown WITH `<select>` tag (Traditional)

### 🔹 HTML Example



✅ **Use Selenium `Select` class**

***

## ✅ Code Using `Select` Class

```java
import org.openqa.selenium.support.ui.Select;

WebElement country = driver.findElement(By.id("country"));

Select select = new Select(country);

// Select by visible text
select.selectByVisibleText("India");

// Select by index
select.selectByIndex(1);

// Select by value
select.selectByValue("USA");
```

✅ **Only works if `<select>` tag exists**

***

## ✅ Get All Options from Select Dropdown

```java
List<WebElement> options = select.getOptions();

for (WebElement opt : options) {
    System.out.println(opt.getText());
}
```

***

# ✅ TYPE 2: Dropdown WITHOUT `<select>` tag

### (Bootstrap / Div / Input based dropdown)

### 🔹 Example:

*   Facebook DOB
*   Bootstrap dropdowns
*   Custom UI

❌ `Select` class **WILL NOT WORK**

✅ Use **click + option selection**

***

## ✅ Example Code (Bootstrap Dropdown)

```java
// Open dropdown
driver.findElement(By.xpath("//div[@aria-label='Select day']")).click();

// Select option
driver.findElement(By.xpath("//div[@role='option' and normalize-space()='1']")).click();
```

***

### ✅ Why this works

*   `aria-label` → stable
*   `role='option'` → identifies option
*   `normalize-space()` → avoids spacing issues

***

## ✅ Reusable Method (Best Practice)

```java
public static void selectCustomDropdown(WebDriver driver,
                                        String dropdownLabel,
                                        String value) {

    // Open dropdown
    driver.findElement(By.xpath("//div[@aria-label='" + dropdownLabel + "']")).click();

    // Select option
    driver.findElement(By.xpath(
            "//div[@role='option' and normalize-space()='" + value + "']")).click();
}
```

✅ Usage:

```java
selectCustomDropdown(driver, "Select day", "1");
selectCustomDropdown(driver, "Select month", "January");
selectCustomDropdown(driver, "Select year", "2026");
```

***

# ✅ TYPE 3: AUTO-SUGGEST / DYNAMIC DROPDOWN

### 🔹 Example:

*   Google search suggestions
*   Amazon search
*   MakeMyTrip city search

Options appear **dynamically while typing**

***

## ✅ Example Code (Auto-Suggest Dropdown)

```java
driver.findElement(By.name("q")).sendKeys("selenium");

List<WebElement> suggestions =
        driver.findElements(By.xpath("//ul/li//span"));

for (WebElement s : suggestions) {
    if (s.getText().contains("selenium tutorial")) {
        s.click();
        break;
    }
}
```

✅ Must:

*   Wait for suggestions
*   Loop and match text

***

# ✅ FULL WORKING EXAMPLE (Your Code Explained)

```java
package seleniumTraining;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.edge.EdgeDriver;

import java.util.List;

public class CheckAndRadio {

    public static void main(String[] args) {

        WebDriver driver = new EdgeDriver();
        driver.get("https://testautomationpractice.blogspot.com/");
        driver.manage().window().maximize();

        // ✅ Select one checkbox
        driver.findElement(By.id("sunday")).click();

        // ✅ Count all checkboxes
        List<WebElement> checkboxes =
                driver.findElements(By.xpath("//input[@type='checkbox']"));

        System.out.println("Total checkboxes: " + checkboxes.size());
    }
}
```

***

# ✅ INTERVIEW QUICK SUMMARY (VERY IMPORTANT)

| Element            | Handling              |
| ------------------ | --------------------- |
| Checkbox           | click(), isSelected() |
| Select dropdown    | `Select` class        |
| Bootstrap dropdown | click + option        |
| Auto-suggest       | sendKeys + loop       |

***

# ✅ WHEN TO USE SELECT CLASS?

✅ Only when:



❌ Never when:



***
