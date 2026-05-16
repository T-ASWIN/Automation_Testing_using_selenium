1.<img width="410" height="231" alt="image" src="https://github.com/user-attachments/assets/0281a9cf-9602-44b9-8e1a-dc8fdd2b9ccf" />




1.parent ::
2.preceding-sibling::
3.following-sibling::
4.ancestor::
5.child::
6.descendant::


***

# 📘 XPath Axes (Simple Explanation + Examples)

## 🔹 1. `parent::`

**Definition:** Selects the **parent (one level above)** of the current element.

### ✅ Examples:

```xpath
//input[@name='search']/parent::div
```

👉 Gets the **div** that contains the input

```xpath
//a[text()='Login']/parent::li
```

👉 Gets the **li** containing the link

***

## 🔹 2. `preceding-sibling::`

**Definition:** Selects all **siblings before (above)** the current element.

### ✅ Examples:

```xpath
//li[text()='Item 3']/preceding-sibling::li
```

👉 Gets Item1, Item2

```xpath
//div[@id='third']/preceding-sibling::div
```

👉 Gets all divs before "third"

***

## 🔹 3. `following-sibling::`

**Definition:** Selects all **siblings after (below)** the current element.

### ✅ Examples:

```xpath
//li[text()='Item 2']/following-sibling::li
```

👉 Gets Item3, Item4

```xpath
//h2[text()='Title']/following-sibling::p
```

👉 Gets paragraphs after heading

***

## 🔹 4. `ancestor::`

**Definition:** Selects **all parents, grandparents, up to root**.

### ✅ Examples:

```xpath
//input[@name='search']/ancestor::form
```

👉 Gets parent form

```xpath
//span[text()='Hi']/ancestor::div
```

👉 Gets all ancestor divs

***

## 🔹 5. `child::`

**Definition:** Selects **direct children** of an element.

### ✅ Examples:

```xpath
//div[@id='menu']/child::a
```

👉 Gets all direct `<a>` inside menu div

```xpath
//ul/child::li
```

👉 Gets list items inside `<ul>`

***

## 🔹 6. `descendant::`

**Definition:** Selects **all children, grandchildren (any level below)**.

### ✅ Examples:

```xpath
//div[@id='menu']/descendant::a
```

👉 Gets all `<a>` inside div (at any level)

```xpath
//form/descendant::input
```

👉 Gets all input fields inside form

***

# ✅ Quick Summary

| Axis              | Meaning          |
| ----------------- | ---------------- |
| parent            | one level up     |
| preceding-sibling | elements before  |
| following-sibling | elements after   |
| ancestor          | all parents      |
| child             | direct children  |
| descendant        | all levels below |

***

💡 **Easy Trick to Remember:**

*   Up → `parent`, `ancestor`
*   Same level → `siblings`
*   Down → `child`, `descendant`

***


