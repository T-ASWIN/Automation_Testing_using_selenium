
***

# ✅ **HashSet (Java)**

`HashSet` is a **class** which **implements the Set interface**.

```java
import java.util.HashSet;
```

***

## ✅ **Features of HashSet (Explanation)**

### **1) Heterogeneous Data – Allowed**

*   `HashSet` can store **different types of objects**.

```java
HashSet hs = new HashSet();
hs.add(10);
hs.add("Java");
hs.add(10.5);
```

***

### **2) Insertion Order – NOT Preserved**

*   Elements are stored using **hashing**
*   Order is **random / unpredictable**

```java
[Java, 10, 10.5]  // order may change
```

***

### **3) Duplicate Elements – NOT Allowed**

*   Only **unique elements** are stored
*   Duplicate elements are **ignored**

```java
hs.add(10);
hs.add(10);   // ignored
```

***

### **4) Null Values – Only ONE Allowed**

*   Multiple nulls are **not allowed**

```java
hs.add(null);
hs.add(null);   // ignored
```

***

### **5) No Index**

*   `HashSet` does **not support index**
*   No `get()` method

***

## ✅ **HashSet Methods with Code**

### **1) add(Object o)**

➡ Adds element to HashSet

```java
HashSet hs = new HashSet();
hs.add("Sam");
hs.add(100);
hs.add(null);

System.out.println(hs);
```

***

### **2) size()**

➡ Returns number of elements

```java
System.out.println(hs.size());
```

***

### **3) remove(Object o)**

➡ Removes specified element

```java
hs.remove("Sam");
System.out.println(hs);
```

***

### **4) contains(Object o)**

➡ Checks whether element exists

```java
System.out.println(hs.contains(100));   // true
```

***

### **5) isEmpty()**

➡ Checks whether HashSet is empty

```java
System.out.println(hs.isEmpty());
```

***

### **6) clear()**

➡ Removes all elements

```java
hs.clear();
System.out.println(hs);
```

***

### **7) iterator()**

➡ Used to traverse elements

```java
Iterator itr = hs.iterator();
while (itr.hasNext()) {
    System.out.println(itr.next());
}
```

***

## ✅ **Example Program**

```java
import java.util.*;

public class HashSetDemo {
    public static void main(String[] args) {

        HashSet<String> hs = new HashSet<>();

        hs.add("Java");
        hs.add("Python");
        hs.add("Java");   // duplicate
        hs.add(null);

        System.out.println(hs);
    }
}
```

✅ Output (order may vary):

    [Python, Java, null]

***

## ✅ **ArrayList vs HashSet (Quick Difference)**

| Feature     | ArrayList     | HashSet       |
| ----------- | ------------- | ------------- |
| Order       | Preserved     | Not preserved |
| Duplicates  | Allowed       | Not allowed   |
| Nulls       | Multiple      | Only one      |
| Index       | Yes           | No            |
| Performance | Slower search | Faster search |

***

