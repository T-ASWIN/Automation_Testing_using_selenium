Here’s your content converted into a clean **README-style notes** with **1–2 line explanations + small examples** ✅

***

# 📘 XPath & DOM Quick Notes (Selenium)

## 🔹 1. XPath

**Definition:** XPath is used to locate elements in XML/HTML documents.  
**Example:**

```xpath
//input[@name='search']
```

***

## 🔹 2. DOM (Document Object Model)

**Definition:** DOM is the tree structure created by the browser from HTML.  
**Example:**

```text
html → body → h1
```

***

## 🔹 3. Types of XPath

### ✅ Absolute XPath

**Definition:** Full path from root (`/html/...`) to element.  
**Example:**

```xpath
/html/body/div/input
```

***

### ✅ Relative XPath

**Definition:** Starts anywhere using `//`, more flexible and preferred.  
**Example:**

```xpath
//input[@name='search']
```

***

## 🔹 4. Tag + Attribute

**Definition:** Locate element using tag and attribute.  
**Example:**

```xpath
//img[@title='MacBook']
```

***

## 🔹 5. Wildcard `*`

**Definition:** `*` matches any tag.  
**Example:**

```xpath
//*[@name='search']
```

***

## 🔹 6. text()

**Definition:** Matches exact visible text.  
**Example:**

```xpath
//a[text()='Login']
```

***

## 🔹 7. contains()

**Definition:** Matches partial value of text/attribute.  
**Example:**

```xpath
//input[contains(@placeholder,'Search')]
```

***

## 🔹 8. starts-with()

**Definition:** Matches values starting with given text.  
**Example:**

```xpath
//input[starts-with(@id,'user_')]
```

***

## 🔹 9. OR Condition

**Definition:** Matches if any one condition is true.  
**Example:**

```xpath
//*[@id='start' or @id='stop']
```

***

## 🔹 10. Dynamic Attributes

**Definition:** Used when values change dynamically.  
**Example:**

```xpath
//*[contains(@id,'user')]
```

***

## 🔹 11. Chained XPath

**Definition:** Navigate parent → child elements.  
**Example:**

```xpath
//div[@id='logo']/a/img
```

***

## 🔹 12. contains(text())

**Definition:** Matches partial visible text.  
**Example:**

```xpath
//div[contains(text(),'Wel')]
```

***

## 🔹 13. text() vs contains(text())

**Exact match:**

```xpath
//div[text()='Welcome']
```

**Partial match:**

```xpath
//div[contains(text(),'Wel')]
```

***

## 🔹 14. contains(.)

**Definition:** Matches full text including nested elements.  
**Example:**

```xpath
//*[contains(.,'Welcome')]
```

***

# ✅ Quick Summary

*   XPath → Locate elements
*   DOM → Page structure
*   Relative XPath → ✅ Preferred
*   `text()` → Exact match
*   `contains()` → Partial match
*   `starts-with()` → Prefix match

***

If you want, I can also convert this into a **PDF or interview cheat sheet** 👍
