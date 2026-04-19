
***

## **ArrayList**

`ArrayList` is a **class** which **implements the List interface**.

***

## ✅ **Features of ArrayList (Explanation)**

### **1) Heterogeneous data – Allowed**

*   `ArrayList` can store **different types of objects** because it stores elements as `Object`.

```java
ArrayList al = new ArrayList();
al.add(10);
al.add("Java");
al.add(10.5);
```

***

### **2) Insertion Order – Preserved (Index based)**

*   Elements are stored in the **same order** in which they are inserted.
*   Each element is stored with an **index** starting from `0`.

```java
al.add("A");   // index 0
al.add("B");   // index 1
```

***

### **3) Duplicate Elements – Allowed**

*   `ArrayList` allows **duplicate values**.

```java
al.add(10);
al.add(10);   // duplicate allowed
```

***

### **4) Multiple Nulls – Allowed**

*   You can store **more than one `null` value**.

```java
al.add(null);
al.add(null);
```

***

# ✅ **ArrayList – Methods with Explanation & Code**

```java
import java.util.*;
```

```java
ArrayList al = new ArrayList();
```

***

## **1) add(Object o)**

➡ Adds an element at the **end** of the list.

```java
al.add(10);
al.add("Java");
al.add(20.5);
System.out.println(al);
```

✅ Output:

    [10, Java, 20.5]

***

## **2) add(int index, Object o)**

➡ Inserts element at a **specific index**.

```java
al.add(1, "Python");
System.out.println(al);
```

✅ Output:

    [10, Python, Java, 20.5]

***

## **3) get(int index)**

➡ Retrieves element from given index.

```java
Object obj = al.get(2);
System.out.println(obj);
```

✅ Output:

    Java

***

## **4) set(int index, Object o)**

➡ Replaces element at specified index.

```java
al.set(0, 100);
System.out.println(al);
```

✅ Output:

    [100, Python, Java, 20.5]

***

## **5) remove(int index)**

➡ Removes element using index.

```java
al.remove(1);
System.out.println(al);
```

✅ Output:

    [100, Java, 20.5]

***

## **6) remove(Object o)**

➡ Removes **first occurrence** of given object.

```java
al.remove("Java");
System.out.println(al);
```

✅ Output:

    [100, 20.5]

***

## **7) size()**

➡ Returns total number of elements.

```java
System.out.println(al.size());
```

✅ Output:

    2

***

## **8) contains(Object o)**

➡ Checks whether element exists.

```java
System.out.println(al.contains(100));
System.out.println(al.contains("Java"));
```

✅ Output:

    true
    false

***

## **9) isEmpty()**

➡ Checks if list is empty.

```java
System.out.println(al.isEmpty());
```

✅ Output:

    false

***

## **10) clear()**

➡ Removes all elements from list.

```java
al.clear();
System.out.println(al);
```

✅ Output:

    []

***

## **11) indexOf(Object o)**

➡ Returns index of **first occurrence**.

```java
al.add(10);
al.add(20);
al.add(10);

System.out.println(al.indexOf(10));
```

✅ Output:

    0

***

## **12) lastIndexOf(Object o)**

➡ Returns index of **last occurrence**.

```java
System.out.println(al.lastIndexOf(10));
```

✅ Output:

    2

***

## **13) iterator()**

➡ Used to traverse elements one by one.

```java
Iterator itr = al.iterator();
while (itr.hasNext()) {
    System.out.println(itr.next());
}
```

✅ Output:

    10
    20
    10

***

## **14) toArray()**

➡ Converts `ArrayList` to array.

```java
Object[] arr = al.toArray();
for (Object o : arr) {
    System.out.println(o);
}
```

***

