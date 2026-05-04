
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

