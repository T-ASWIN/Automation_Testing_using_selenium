
***

# ✅ 1. What is a Map?

A **Map** stores data in **key–value pairs**.

*   Each **key is unique**
*   A **value can be duplicate**
*   It is very useful for fast lookup, insertion, and deletion

***

# 🟦 Java Map (Collections Framework)

## ✅ Common Rules

1.  Keys must be **unique**
2.  Only **one null key** is allowed (in `HashMap`)
3.  Multiple null values are allowed
4.  Stored as **(key → value)** pairs

***

## ✅ Creating a Map

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Map<Integer, String> map = new HashMap<>();
    }
}
```

***

## ✅ Important Methods of Map

### 1. put() → Insert data

```java
map.put(1, "Apple");
map.put(2, "Banana");
map.put(3, "Cherry");
```

***

### 2. get() → Retrieve value

```java
System.out.println(map.get(1));  // Output: Apple
```

***

### 3. remove() → Delete entry

```java
map.remove(2);  // Removes Banana
```

***

### 4. containsKey() / containsValue()

```java
System.out.println(map.containsKey(1));  // true
System.out.println(map.containsValue("Apple")); // true
```

***

### 5. size()

```java
System.out.println(map.size());  // Number of entries
```

***

### 6. keySet() → Get all keys

```java
for (Integer key : map.keySet()) {
    System.out.println(key);
}
```

***

### 7. values() → Get all values

```java
for (String value : map.values()) {
    System.out.println(value);
}
```

***

### 8. entrySet() → Key + Value together

```java
for (Map.Entry<Integer, String> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " -> " + entry.getValue());
}
```

***

## ✅ Complete Java Example

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {

        Map<Integer, String> map = new HashMap<>();

        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Mango");

        System.out.println("Value for key 1: " + map.get(1));

        for (Map.Entry<Integer, String> e : map.entrySet()) {
            System.out.println(e.getKey() + " : " + e.getValue());
        }

        map.remove(2);

        System.out.println("After removal: " + map);
    }
}
```

***
