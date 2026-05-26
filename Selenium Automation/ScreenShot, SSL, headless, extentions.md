
***

# ✅ 1. Screenshot in Selenium (3 Ways)

## 🔹 A) Full Page Screenshot

This captures the entire visible browser window.

### ✅ Code:

```java
package selenium_training.Mine;

import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import java.io.File;
import java.nio.file.Files;
import java.time.Duration;

public class Screenshots {
    public static void main(String[] args) throws Exception {

        WebDriver driver = new ChromeDriver();
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
        driver.get("https://testautomationpractice.blogspot.com/");
        driver.manage().window().maximize();

        // Full page screenshot
        TakesScreenshot ts = (TakesScreenshot) driver;
        File sourceFile = ts.getScreenshotAs(OutputType.FILE);

        File targetFile = new File(System.getProperty("user.dir") + "\\ScreenShot\\fullPage.png");
        Files.copy(sourceFile.toPath(), targetFile.toPath());

        driver.quit();
    }
}
```

***

## 🔹 B) Specific Section (Area of Page)

Capture a **particular section** using WebElement.

### ✅ Code:

```java
WebElement section = driver.findElement(By.xpath("//*[@id='HTML1']"));

File sourceFile = section.getScreenshotAs(OutputType.FILE);
File targetFile = new File(System.getProperty("user.dir") + "\\ScreenShot\\section.png");

Files.copy(sourceFile.toPath(), targetFile.toPath());
```

***

## 🔹 C) Specific Web Element Screenshot

Capture **one element only** (e.g., button, textbox).

### ✅ Code:

```java
WebElement element = driver.findElement(By.id("name")); // Example element

File sourceFile = element.getScreenshotAs(OutputType.FILE);
File targetFile = new File(System.getProperty("user.dir") + "\\ScreenShot\\element.png");

Files.copy(sourceFile.toPath(), targetFile.toPath());
```

***

# ⚠️ Important Fix in Your Code

You used:

```java
sourseFile.renameTo(targetFile);
```

❌ Not recommended (may fail silently)

✅ Use:

```java
Files.copy(sourceFile.toPath(), targetFile.toPath());
```

***

# ✅ 2. ChromeOptions (Advanced Browser Config)

## 🔹 A) Headless Mode

### ✅ Code:

```java
ChromeOptions options = new ChromeOptions();
options.addArguments("--headless=new");

WebDriver driver = new ChromeDriver(options);
```

### ✔ Advantages:

* Faster execution
* Runs in background
* Good for CI/CD pipelines

### ❌ Disadvantages:

* Cannot see execution visually
* Debugging is harder

***

## 🔹 B) Remove "Chrome is being controlled" Message

```java
ChromeOptions options = new ChromeOptions();
options.setExperimentalOption("excludeSwitches",
        new String[]{"enable-automation"});

WebDriver driver = new ChromeDriver(options);
```

***

## 🔹 C) Incognito Mode

```java
ChromeOptions options = new ChromeOptions();
options.addArguments("--incognito");

WebDriver driver = new ChromeDriver(options);
```

***

## 🔹 D) Add Browser Extension (CRX file)

```java
ChromeOptions options = new ChromeOptions();
options.addExtensions(new File("C:\\Drivers\\SelectorsHub.crx"));

WebDriver driver = new ChromeDriver(options);
```

***

## 🔹 E) Block Ads (Using Extension)

You can't block ads directly using Selenium code, but you can:

✅ Install extensions like:

* uBlock Origin
* AdBlock

Then load via:

```java
options.addExtensions(new File("C:\\Drivers\\adblock.crx"));
```

***

# ✅ 3. Other Browser Options

Similar classes exist:

```java
ChromeOptions
EdgeOptions
FirefoxOptions
```

Example:

```java
EdgeOptions options = new EdgeOptions();
WebDriver driver = new EdgeDriver(options);
```

***

# ✅ 4. SSL Certificate Handling

Sometimes site shows:
**"Your connection is not private"**

### ✅ Code:

```java
ChromeOptions options = new ChromeOptions();
options.setAcceptInsecureCerts(true);

WebDriver driver = new ChromeDriver(options);
```

***

# ✅ Final Combined Example

```java
ChromeOptions options = new ChromeOptions();
options.addArguments("--incognito");
options.addArguments("--headless=new");
options.setAcceptInsecureCerts(true);

WebDriver driver = new ChromeDriver(options);
driver.get("https://testautomationpractice.blogspot.com/");
```

***

# ✅ Summary

| Feature                   | Code Method                    |
| ------------------------- | ------------------------------ |
| Full Screenshot           | `TakesScreenshot`              |
| Section Screenshot        | `WebElement.getScreenshotAs()` |
| Element Screenshot        | Same as above                  |
| Headless                  | `--headless=new`               |
| Incognito                 | `--incognito`                  |
| Remove automation message | `excludeSwitches`              |
| Extensions                | `addExtensions()`              |
| SSL issues                | `setAcceptInsecureCerts(true)` |

***

