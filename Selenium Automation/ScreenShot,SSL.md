1.screenshot is an interface 
2.how to take screenshots there there three ways

full page
specific area of the page  or specific section f the page 
web element


package selenium_training.Mine;

import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;

import java.io.File;
import java.time.Duration;

public class Screenshots {

    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

        driver.get("https://testautomationpractice.blogspot.com/");
        driver.manage().window().maximize();


//        TakesScreenshot ts=(TakesScreenshot) driver;
//       File sourseFile = ts.getScreenshotAs(OutputType.FILE);
//       File targetFile = new File(System.getProperty("user.dir")+"\\ScreenShot\\fullPage.png");
//       sourseFile.renameTo(targetFile);


        WebElement ts = driver.findElement(By.xpath("//*[@id=\"HTML1\"]"));
        File sourseFile = ts.getScreenshotAs(OutputType.FILE);
        File targetFile = new File(System.getProperty("user.dir")+"\\ScreenShot\\fullPage.png");
       sourseFile.renameTo(targetFile);


       
    }
}






ChromeOptions
EdgeOptions
FirefoxOptions
etc...

