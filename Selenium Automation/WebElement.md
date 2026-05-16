In Selenium, a WebElement represents a single HTML element present in the browser’s DOM.

Examples of HTML elements:

Button

Textbox

Link

Checkbox

Dropdown


All of these become WebElement objects in Selenium.


---

Simple Definition

> WebElement is an interface in Selenium used to represent and interact with a specific element on a webpage.




---

Example

HTML:

<input type="text" id="username">

Selenium:

WebElement userBox = driver.findElement(By.id("username"));

Here:

driver.findElement() searches the DOM

It finds the <input>

Returns it as a WebElement



---

Why Do We Use WebElement?

Because Selenium needs a reference to the element before performing actions.

Example actions:

click()

sendKeys()

getText()

clear()

isDisplayed()



---

Example Actions

WebElement loginBtn = driver.findElement(By.id("login"));

loginBtn.click();

WebElement name = driver.findElement(By.id("username"));

name.sendKeys("Aswin");


---

Relationship Between WebDriver and WebElement

WebDriver → Controls browser
WebElement → Represents element inside browser DOM

Example:

WebDriver driver = new ChromeDriver();

WebElement btn =
driver.findElement(By.id("submit"));

Here:

driver controls the browser

btn represents one DOM element



---

Common WebElement Methods

Method	Purpose

click()	Click element
sendKeys()	Type text
getText()	Get visible text
clear()	Clear textbox
isDisplayed()	Check visibility
isEnabled()	Check enabled state
getAttribute()	Get attribute value



---

Real-World Analogy

Imagine:

Browser = Building

DOM = Rooms inside building

WebDriver = Security controller

WebElement = Specific room/object


WebDriver controls the building. WebElement is the exact object you want to interact with.


---

Short Interview Answer

> WebElement in Selenium represents an HTML element in the DOM. It is used to perform actions like clicking, typing, reading text, and checking properties of webpage elements.
