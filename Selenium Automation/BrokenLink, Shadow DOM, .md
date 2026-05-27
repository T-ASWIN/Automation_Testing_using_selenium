
***

# ✅ 1. Broken Links

### 🔹 Concept

A **broken link** is a URL that returns an error status code.

* `status < 400` → ✅ Valid link
* `status >= 400` → ❌ Broken link

***

### 🔹 Steps

1. Get all links (`<a>` tags)
2. Extract `href`
3. Send HTTP request
4. Check status code

***

### ✅ Java (Selenium + HttpURLConnection)

```java
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.List;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrokenLinks {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("https://example.com");

        List<WebElement> links = driver.findElements(By.tagName("a"));

        for (WebElement link : links) {
            String url = link.getAttribute("href");

            if (url == null || url.isEmpty()) {
                continue;
            }

            try {
                URL linkUrl = new URL(url);
                HttpURLConnection conn = (HttpURLConnection) linkUrl.openConnection();
                conn.setConnectTimeout(3000);
                conn.connect();

                int statusCode = conn.getResponseCode();

                if (statusCode >= 400) {
                    System.out.println(url + " --> Broken Link (" + statusCode + ")");
                } else {
                    System.out.println(url + " --> Valid Link (" + statusCode + ")");
                }

            } catch (Exception e) {
                System.out.println(url + " --> Exception occurred");
            }
        }

        driver.quit();
    }
}
```

***

# ✅ 2. Shadow DOM

## 🔹 Key Concepts

| Term        | Meaning                          |
| ----------- | -------------------------------- |
| Main DOM    | Normal HTML page                 |
| Shadow DOM  | Hidden DOM inside element        |
| Shadow Host | Element that contains shadow DOM |
| Shadow Root | Root of shadow DOM               |

***

### ❗ Important Rule

➡️ **XPath cannot directly access Shadow DOM**\
➡️ ✅ Use **JavaScript / CSS / Selenium 4 ShadowRoot**

***

### ✅ Example HTML Concept



***

### ✅ Selenium 4 (Direct ShadowRoot handling)

```java
WebElement shadowHost = driver.findElement(By.cssSelector("custom-element"));

SearchContext shadowRoot = shadowHost.getShadowRoot();

WebElement input = shadowRoot.findElement(By.cssSelector("#username"));
input.sendKeys("Hello");
```

***

### ✅ Using JavaScript Executor (Old Way)

```java
WebElement shadowHost = driver.findElement(By.cssSelector("custom-element"));

JavascriptExecutor js = (JavascriptExecutor) driver;

WebElement shadowRoot = (WebElement) js.executeScript(
    "return arguments[0].shadowRoot", shadowHost);

WebElement input = shadowRoot.findElement(By.cssSelector("#username"));
input.sendKeys("Hello");
```

***

# ✅ 3. SVG Elements

## 🔹 Problem

SVG elements belong to a different XML namespace.

➡️ Normal XPath (`//svg`) ❌ may not work\
➡️ Use `name()` function ✅

***

## ✅ Correct XPath for SVG

```xpath
//*[name()='svg']
```

***

### ✅ Examples

#### 1. Select path element

```xpath
//*[name()='path']
```

#### 2. With attribute condition

```xpath
//*[name()='path' and contains(@d,'M256,302c8')]
```

#### 3. SVG inside anchor

```xpath
//a[normalize-space()='']// *[name()='svg']
```

***

## ✅ Selenium Java Example

```java
WebElement svgElement = driver.findElement(
    By.xpath("//*[name()='svg']")
);

WebElement path = driver.findElement(
    By.xpath("//*[name()='path' and contains(@d,'M256,302c8')]")
);

path.click();
```

***

## 🔹 Important Notes

* SVG elements **don’t behave like normal HTML tags**
* `name()` is required because of namespace handling
* You usually:
  * Identify SVG using `name()='svg'`
  * Then drill down to child elements (`path`, `circle`, etc.)

***

# ✅ Summary

### 🔹 Broken Links

* Use HTTP status codes
* `>=400` = broken

***

### 🔹 Shadow DOM

* XPath ❌
* CSS / JS ✅
* Access via `getShadowRoot()`

***

### 🔹 SVG Elements

* Use `name()='tag'`
* Namespace handling required

***
