1.tageName,attributes,value
control+shift+o

2. basics locators
id
name
linkText
partialLinkText

TagName
classname

CSS selector
XPath


3.
## What is WebElement?

1.  **WebElement is an interface in Selenium.**
2.  It represents an **HTML element** on a web page.
3.  It is used to **perform actions** on web elements like buttons, text boxes, links, etc.

***

## Example of WebElements

*   Text box
*   Button
*   Link
*   Checkbox
*   Radio button
*   Dropdown

***

## How WebElement is used

WebElement is used to interact with elements on a webpage.

### Example (Java):

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Example {
    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();
        driver.get("https://www.google.com");

        WebElement searchBox = driver.findElement(By.name("q"));

        searchBox.sendKeys("Selenium");
    }
}
```

***

## Common Methods of WebElement

*   `sendKeys()` → Enter text
*   `click()` → Click element
*   `getText()` → Get text from element
*   `clear()` → Clear input field
*   `isDisplayed()` → Check visibility
*   `isEnabled()` → Check if enabled

***

