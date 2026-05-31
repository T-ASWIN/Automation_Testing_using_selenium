
***

## ✅ 1. Java Program to Check Whether a Number is Prime

```java
class PrimeNumber {
    public static void main(String[] args) {
        int num = 7;
        boolean isPrime = true;

        if (num <= 1) {
            isPrime = false;
        } else {
            for (int i = 2; i <= num / 2; i++) {
                if (num % i == 0) {
                    isPrime = false;
                    break;
                }
            }
        }

        if (isPrime)
            System.out.println("Prime Number");
        else
            System.out.println("Not a Prime Number");
    }
}
```

✅ Prime → divisible only by 1 and itself.

***

## ✅ 2. Java Program to Reverse a String

```java
class ReverseString {
    public static void main(String[] args) {
        String str = "Java";
        String rev = "";

        for (int i = str.length() - 1; i >= 0; i--) {
            rev = rev + str.charAt(i);
        }

        System.out.println("Reversed String: " + rev);
    }
}
```

***

## ✅ 3. Swap Two Numbers Without Using Third Variable

```java
class Swap {
    public static void main(String[] args) {
        int a = 5, b = 10;

        a = a + b;
        b = a - b;
        a = a - b;

        System.out.println("a = " + a + ", b = " + b);
    }
}
```

***

## ✅ 4. Find the Largest Number in an Array

```java
class LargestArray {
    public static void main(String[] args) {
        int[] arr = {10, 45, 2, 89, 30};
        int max = arr[0];

        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }

        System.out.println("Largest number: " + max);
    }
}
```

***

## ✅ 5. Find Repeated Words in a String

```java
import java.util.*;

class RepeatedWords {
    public static void main(String[] args) {
        String str = "java is easy and java is powerful";
        String[] words = str.split(" ");

        Map<String, Integer> map = new HashMap<>();

        for (String word : words) {
            map.put(word, map.getOrDefault(word, 0) + 1);
        }

        for (String word : map.keySet()) {
            if (map.get(word) > 1) {
                System.out.println(word + " : " + map.get(word));
            }
        }
    }
}
```

***

## ✅ 6. Count Vowels in a String

```java
class CountVowels {
    public static void main(String[] args) {
        String str = "automation";
        int count = 0;

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);

            if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u') {
                count++;
            }
        }

        System.out.println("Vowel count: " + count);
    }
}
```

***

## ✅ 7. Java Program to Find the Lowest Number

```java
class LowestNumber {
    public static void main(String[] args) {
        int[] arr = {10, 5, 20, 3, 25};
        int min = arr[0];

        for (int i = 1; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i];
            }
        }

        System.out.println("Lowest number: " + min);
    }
}
```

***

## ✅ 8. Fibonacci Series

```java
class Fibonacci {
    public static void main(String[] args) {
        int n = 10, a = 0, b = 1;

        System.out.print("Fibonacci Series: ");

        for (int i = 1; i <= n; i++) {
            System.out.print(a + " ");
            int c = a + b;
            a = b;
            b = c;
        }
    }
}
```

✅ Series: `0 1 1 2 3 5 8 ...`

***

## ✅ 9. Find Second Largest Element in a Table (Array)

```java
class SecondLargest {
    public static void main(String[] args) {
        int[] arr = {10, 45, 23, 89, 67};

        int largest = arr[0];
        int secondLargest = arr[0];

        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > largest) {
                secondLargest = largest;
                largest = arr[i];
            } else if (arr[i] > secondLargest && arr[i] != largest) {
                secondLargest = arr[i];
            }
        }

        System.out.println("Second Largest: " + secondLargest);
    }
}
```

***

## ✅ INTERVIEW QUICK TIP

Be ready to explain:

* **Logic**
* **Time complexity**
* **Edge cases**

***

