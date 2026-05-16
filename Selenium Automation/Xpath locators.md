1. XPath → XML Path Language

XPath stands for XML Path Language.

It is used to locate elements in:

XML documents

HTML documents (DOM)


In Selenium, XPath is mainly used to identify web elements on a webpage.


---

Why XPath is Needed?

Sometimes elements:

don’t have ID

don’t have name

have dynamic attributes


So XPath helps Selenium find elements using:

tag names

attributes

text

relationships



---

Example

HTML:

<input type="text" name="search">

XPath:

//input[@name='search']

Meaning:

> Find an input tag whose name attribute is search.




---

2. DOM → Document Object Model

DOM stands for Document Object Model.

When a webpage loads:

1. Browser reads HTML


2. Converts it into a tree structure


3. This structure is called DOM




---

Example HTML

<html>
  <body>
    <h1>Hello</h1>
  </body>
</html>

DOM Tree:

Document
 └── html
      └── body
           └── h1


---

Why DOM is Important in Selenium?

Selenium works on the DOM, not directly on raw HTML.

When Selenium searches:

driver.findElement(By.xpath("//h1"));

It checks the DOM structure.


---

3. Types of XPath

There are 2 types:

1. Absolute XPath


2. Relative XPath




---

3.1 Absolute XPath (Full XPath)

Definition

Absolute XPath starts from the root node and traverses every node.

Example:

/html/body/header/div/div/div[2]/div/input


---

Characteristics

Starts with /

Begins from root node

Traverses each node completely

Very lengthy

Breaks easily if structure changes



---

Problem

If one <div> changes:

<div></div>

Entire XPath may fail.

So it is not preferred in automation.


---

3.2 Relative XPath (Partial XPath)

Definition

Relative XPath directly finds element using attributes.

Example:

//*[@name='search']


---

Characteristics

Starts with //

Uses attributes

Short and readable

Faster and flexible

Preferred in Selenium



---

Which XPath is Preferred?

✅ Relative XPath

Because:

Stable

Easy to maintain

Less chances of failure



---

Difference Between Absolute and Relative XPath

Absolute XPath	Relative XPath

Starts with /	Starts with //
Begins from root	Begins anywhere
No attributes used usually	Uses attributes
Traverses all nodes	Directly jumps to element
Long	Short
Fragile	Stable



---

Syntax of XPath

1. Using Tag + Attribute

//tagname[@attribute='value']

Example:

//img[@title='MacBook']

Meaning:

> Find img tag whose title is MacBook




---

2. Using Wildcard *

//*[@attribute='value']

Example:

//*[@name='search']

Meaning:

> Find any tag with name='search'




---

XPath with Inner Text → text()

Used when element text is visible.


---

Example 1

//a[text()='Desktops']

Meaning:

> Find <a> tag having exact text Desktops




---

Example 2

//a[text()='MacBook']


---

Link Text vs Inner Text

HTML:

<a href="https://xyz.com">Click Me</a>

Link text → YES

Inner text → YES


Because anchor tag contains visible text.


---

HTML:

<div>welcome</div>

Link text → NO

Inner text → YES


Because div is not a hyperlink.


---

XPath with contains()

Used when attribute value is partially known.


---

Syntax

//tag[contains(@attribute,'value')]


---

Example

//input[contains(@placeholder,'Sea')]

Matches:

<input placeholder="Search products">

Because it contains "Sea".


---

Handling Dynamic Attributes

Some applications generate changing IDs.

Example:

start123
start456
start789

Exact match won't work.

So we use:

contains()

starts-with()

OR condition



---

OR Condition

//*[@id='start' or @id='stop']

Meaning:

> Match id=start OR id=stop




---

contains()

//*[contains(@id,'st')]

Matches:

start

stop

staging



---

starts-with()

//*[starts-with(@id,'st')]

Matches values beginning with "st".


---

Dynamic Name Examples

Example 1

xyz001
xyz002
xyz003

XPath:

//*[contains(@name,'xyz')]

or

//*[starts-with(@name,'xyz')]


---

Example 2

1xyz
2xyz
3xyz

XPath:

//*[contains(@name,'xyz')]


---

Chained XPath

Used to travel parent → child.


---

Example

//div[@id='logo']/a/img

Meaning:

1. Find div with id='logo'


2. Inside it find <a>


3. Inside it find <img>




---

text() vs contains(text())

Exact Text

//div[text()='Welcome']

Exact match only.


---

Partial Text

//div[contains(text(),'Wel')]

Matches:

Welcome

Welcoming



---

contains(.)

. represents complete text inside element.

//*[contains(.,'Welcome')]

Useful when:

nested tags exist

mixed text exists



---

Final Quick Summary

Concept	Purpose

XPath	Locate elements
DOM	Browser structure of webpage
Absolute XPath	Full path from root
Relative XPath	Direct flexible path
text()	Exact text matching
contains()	Partial matching
starts-with()	Prefix matching
Chained XPath	Parent-child navigation
