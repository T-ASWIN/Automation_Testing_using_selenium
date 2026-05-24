
***

# ✅ 1. Mouse Actions in Selenium

Selenium provides the **`Actions` class** to perform advanced user interactions like:

| Action       | Method            |
| ------------ | ----------------- |
| Mouse Hover  | `moveToElement()` |
| Right Click  | `contextClick()`  |
| Double Click | `doubleClick()`   |
| Drag & Drop  | `dragAndDrop()`   |

***

## ✅ Example: Mouse Actions Code

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class MouseActionsDemo {
    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();
        driver.get("https://demoqa.com/buttons");

        Actions actions = new Actions(driver);

        // Locate element
        WebElement button = driver.findElement(By.id("rightClickBtn"));

        // Right click
        actions.contextClick(button).perform();

        // Double click
        WebElement dblClickBtn = driver.findElement(By.id("doubleClickBtn"));
        actions.doubleClick(dblClickBtn).perform();
    }
}
```

***

## ✅ Drag and Drop Example

```java
WebElement source = driver.findElement(By.id("draggable"));
WebElement target = driver.findElement(By.id("droppable"));

Actions actions = new Actions(driver);

actions.dragAndDrop(source, target).perform();
```

***

## ✅ Mouse Hover Example

```java
WebElement menu = driver.findElement(By.id("menu"));

Actions actions = new Actions(driver);

actions.moveToElement(menu).perform();
```

***

# ✅ 2. `build()` vs `perform()`

### ✅ perform()

* Executes the action immediately

```java
actions.doubleClick(element).perform();
```

***

### ✅ build()

* Combines multiple actions into one **Action object**

```java
actions.moveToElement(ele)
       .click()
       .build()
       .perform();
```

👉 `build()` → prepares action\
👉 `perform()` → executes action

***

# ✅ 3. getText() vs getAttribute()

***

## ✅ Example 1



```java
element.getText();          // ✅ returns "welcome"
element.getAttribute("id"); // ✅ returns "xyz"
```

***

## ✅ Example 2



```java
element.getText();              // ❌ returns ""
element.getAttribute("value");  // ✅ returns "welcome"
```

***

## ✅ Key Difference

| Method           | What it returns                   |
| ---------------- | --------------------------------- |
| `getText()`      | Visible **inner text** of element |
| `getAttribute()` | Value of HTML attribute           |

***

## ✅ Important Note

👉 For **input fields**, always use:

```java
getAttribute("value")
```

👉 Because `getText()` does NOT work for input fields

***

# ✅ 4. Actions vs Action

***

## ✅ Actions (Class)

* Predefined Selenium class
* Used to **create complex user actions**

```java
Actions actions = new Actions(driver);
```

***

## ✅ Action (Interface)

* Represents a **single built action**
* Stored using `build()`

```java
Action act = actions.moveToElement(element).click().build();

act.perform();
```

***

## ✅ Example: Actions vs Action

```java
import org.openqa.selenium.interactions.Action;
import org.openqa.selenium.interactions.Actions;

Actions actions = new Actions(driver);

// Create action
Action act = actions.moveToElement(element)
                    .click()
                    .build();

// Execute action
act.perform();
```

***

# ✅ Simple Understanding

| Term        | Meaning                                 |
| ----------- | --------------------------------------- |
| **Actions** | Builder class (creates actions)         |
| **Action**  | Final action object (stored & executed) |

***

# ✅ Final Summary

* ✅ `Actions` → used for advanced mouse/keyboard interactions
* ✅ `perform()` → executes action
* ✅ `build()` → creates action object
* ✅ `getText()` → visible text
* ✅ `getAttribute()` → attribute value
* ✅ `Action` → interface storing built action

***
