
***

## 1️⃣ `+` (One or more times)

### Meaning

    +  →  at least 1 time

### Example

```java
String regex = "a+";
```

✅ **Matches**

*   `"a"`
*   `"aa"`
*   `"aaa"`

❌ **Does NOT match**

*   `""` (empty string)

### Java Example

```java
System.out.println("a".matches("a+"));    // true
System.out.println("aa".matches("a+"));   // true
System.out.println("".matches("a+"));     // false
```

***

## 2️⃣ `*` (Zero or more times)

### Meaning

    *  →  0 or more times

### Example

```java
String regex = "a*";
```

✅ **Matches**

*   `""` (empty string)
*   `"a"`
*   `"aaa"`

### Java Example

```java
System.out.println("".matches("a*"));     // true
System.out.println("a".matches("a*"));    // true
System.out.println("aaa".matches("a*"));  // true
```

✅ **Key difference from `+`**

*   `*` allows **zero**
*   `+` requires **at least one**

***

## 3️⃣ `{}` (Exact or range of repetitions)

### a) Exact number `{n}`

    {n} → exactly n times

```java
String regex = "a{3}";
```

✅ Matches: `"aaa"`  
❌ Not matches: `"aa"`, `"aaaa"`

```java
System.out.println("aaa".matches("a{3}"));  // true
```

***

### b) Minimum number `{n,}`

    {n,} → n or more times

```java
String regex = "a{2,}";
```

✅ Matches:

*   `"aa"`
*   `"aaa"`
*   `"aaaa"`

```java
System.out.println("aa".matches("a{2,}"));   // true
```

***

### c) Range `{n,m}`

    {n,m} → between n and m times

```java
String regex = "a{2,4}";
```

✅ Matches:

*   `"aa"`
*   `"aaa"`
*   `"aaaa"`

❌ Not matches:

*   `"a"`
*   `"aaaaa"`

```java
System.out.println("aaa".matches("a{2,4}"));  // true
```

***

## 🔁 Comparison Table

| Quantifier | Meaning        |
| ---------- | -------------- |
| `a+`       | 1 or more `a`  |
| `a*`       | 0 or more `a`  |
| `a{3}`     | Exactly 3 `a`  |
| `a{2,}`    | At least 2 `a` |
| `a{2,4}`   | 2 to 4 `a`     |

***

## ✅ Real‑world Example (Phone number)

```java
String regex = "\\d{10}";
```

✔ Matches: `"9876543210"`  
❌ Not matches: `"98765"`

***

***

## 1️⃣ `[]` → Character class (ANY ONE character)

### Meaning

Matches **any one character** inside the brackets.

### Example

```java
"[abc]"
```

✅ Matches:

*   `"a"`
*   `"b"`
*   `"c"`

❌ Does NOT match:

*   `"ab"` (only one character allowed)

```java
System.out.println("a".matches("[abc]")); // true
System.out.println("d".matches("[abc]")); // false
```

***

## 2️⃣ `[^ ]` → Negated character class (NOT)

### Meaning

`^` **inside `[]`** means **NOT**  
Matches **any character except** those inside brackets.

### Example

```java
"[^abc]"
```

✅ Matches:

*   `"d"`
*   `"1"`
*   `"@"`

❌ Does NOT match:

*   `"a"`
*   `"b"`

```java
System.out.println("x".matches("[^abc]")); // true
System.out.println("a".matches("[^abc]")); // false
```

***

## 3️⃣ `[a-z]` → Character range

### Meaning

Matches **any lowercase letter** from `a` to `z`.

### Example

```java
"[a-z]"
```

✅ Matches:

*   `"a"`
*   `"m"`
*   `"z"`

❌ Does NOT match:

*   `"A"`
*   `"1"`

```java
System.out.println("k".matches("[a-z]")); // true
System.out.println("K".matches("[a-z]")); // false
```

✅ You can combine:

```java
"[a-zA-Z]"
```

→ matches both lowercase and uppercase letters.

***

## 4️⃣ `\s` → Whitespace character

### Meaning

Matches **any whitespace**:

*   space
*   tab (`\t`)
*   newline (`\n`)

### Example

```java
"\\s"
```

⚠️ In Java, use **double backslash**.

```java
System.out.println(" ".matches("\\s"));   // true
System.out.println("\n".matches("\\s"));  // true
System.out.println("a".matches("\\s"));   // false
```

***

## 5️⃣ `\d` → Digit

### Meaning

Matches **any digit (0–9)**

### Example

```java
"\\d"
```

✅ Matches:

*   `"0"`
*   `"5"`
*   `"9"`

❌ Does NOT match:

*   `"a"`

```java
System.out.println("5".matches("\\d")); // true
System.out.println("a".matches("\\d")); // false
```

✅ For multiple digits:

```java
"\\d+"
```

***

## 6️⃣ `^[]$` → Start and end anchors

### Meaning

*   `^` → start of string
*   `$` → end of string

Ensures **FULL match**, not partial.

### Example

```java
"^[a-z]+$"
```

✅ Matches:

*   `"java"`
*   `"regex"`

❌ Does NOT match:

*   `"Java123"`
*   `"java!"`

```java
System.out.println("java".matches("^[a-z]+$"));   // true
System.out.println("java123".matches("^[a-z]+$"));// false
```

***

## 🔁 Combined Real Example

### Validate **only lowercase letters and spaces**

```java
String regex = "^[a-z\\s]+$";
```

✅ `"hello world"`  
❌ `"Hello123"`

***

## ✅ Quick Summary Table

| Regex   | Meaning              |
| ------- | -------------------- |
| `[]`    | Any one character    |
| `[^ ]`  | NOT these characters |
| `[a-z]` | Lowercase letters    |
| `\s`    | Whitespace           |
| `\d`    | Digit (0–9)          |
| `^...$` | Full string match    |

***


