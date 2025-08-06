### 1. String Manipulation
### a) Reverse a String

```bash
public class ReverseString {
    public static void main(String[] args) {
        String str = "Ideas2IT";
        String reversed = new StringBuilder(str).reverse().toString();
        System.out.println(reversed);
    }
}
```

### b) Reverse a string without library functions
```bash
public class ReverseString {
    public static void main(String[] args) {
        String str = "Ideas2IT";
        String rev = "";
        for (int i = str.length() - 1; i >= 0; i--) {
            rev += str.charAt(i);
        }
        System.out.println(rev);
    }
}
```

### b) Palindrome Check

```bash
public class PalindromeCheck {
    public static void main(String[] args) {
        String str = "madam";
        String rev = new StringBuilder(str).reverse().toString();
        System.out.println(str.equalsIgnoreCase(rev) ? "Palindrome" : "Not Palindrome");
    }
}
```
### c) Anagram Check

```bash
import java.util.Arrays;
public class AnagramCheck {
    public static void main(String[] args) {
        String s1 = "listen", s2 = "silent";
        char[] a1 = s1.toCharArray();
        char[] a2 = s2.toCharArray();
        Arrays.sort(a1);
        Arrays.sort(a2);
        System.out.println(Arrays.equals(a1, a2) ? "Anagram" : "Not Anagram");
    }
}
```
### d) Count vowels and consonants

```bash
public class VowelConsonantCount {
    public static void main(String[] args) {
        String str = "Ideas2IT".toLowerCase();
        int vowels = 0, consonants = 0;
        for (char c : str.toCharArray()) {
            if (c >= 'a' && c <= 'z') {
                if ("aeiou".indexOf(c) != -1) vowels++;
                else consonants++;
            }
        }
        System.out.println("Vowels: " + vowels + ", Consonants: " + consonants);
    }
}
```
### 2. Array Problems
### a) Find Duplicates in an Array

```bash
import java.util.HashSet;

public class FindDuplicates {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 2, 4, 5, 1};
        HashSet<Integer> seen = new HashSet<>();
        for (int num : arr) {
            if (!seen.add(num)) {
                System.out.println("Duplicate: " + num);
            }
        }
    }
}
```
### b) Maximum Subarray Sum (Kadane’s Algorithm)

```bash
public class KadaneAlgorithm {
    public static void main(String[] args) {
        int[] arr = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
        int maxSum = arr[0], currentSum = arr[0];
        for (int i = 1; i < arr.length; i++) {
            currentSum = Math.max(arr[i], currentSum + arr[i]);
            maxSum = Math.max(maxSum, currentSum);
        }
        System.out.println("Max Subarray Sum: " + maxSum);
    }
}
```

### c) Remove duplicates from a sorted array

```bash
public class RemoveDuplicates {
    public static void main(String[] args) {
        int[] arr = {1, 1, 2, 2, 3, 4, 4};
        int n = arr.length;
        int index = 1;
        for (int i = 1; i < n; i++) {
            if (arr[i] != arr[i - 1]) {
                arr[index++] = arr[i];
            }
        }
        for (int i = 0; i < index; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}
```
### d) Find second largest number

```bash
public class SecondLargest {
    public static void main(String[] args) {
        int[] arr = {10, 5, 8, 20, 15};
        int first = Integer.MIN_VALUE, second = Integer.MIN_VALUE;
        for (int num : arr) {
            if (num > first) {
                second = first;
                first = num;
            } else if (num > second && num != first) {
                second = num;
            }
        }
        System.out.println("Second Largest: " + second);
    }
}
```
### 3. Basic Recursion
### Factorial using recursion

```bash
public class FactorialRecursion {
    static int factorial(int n) {
        if (n == 0) return 1;
        return n * factorial(n - 1);
    }
    public static void main(String[] args) {
        System.out.println(factorial(5)); // Output: 120
    }
}
```

### b) Fibonacci series

```bash
public class Fibonacci {
    static int fib(int n) {
        if (n <= 1) return n;
        return fib(n - 1) + fib(n - 2);
    }
    public static void main(String[] args) {
        int n = 6;
        for (int i = 0; i < n; i++) {
            System.out.print(fib(i) + " ");
        }
    }
}
```

### 4. Pattern Printing
### Example: Right triangle pattern
```bash
public class Pattern {
    public static void main(String[] args) {
        int n = 5;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```
### 5. Searching & Sorting
### a) Linear Search

```bash
public class LinearSearch {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40};
        int target = 30;
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                System.out.println("Found at index: " + i);
                return;
            }
        }
        System.out.println("Not Found");
    }
}
```
### b) Binary Search (Array must be sorted)

```bash
public class BinarySearch {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int target = 30;
        int low = 0, high = arr.length - 1;
        while (low <= high) {
            int mid = (low + high) / 2;
            if (arr[mid] == target) {
                System.out.println("Found at index: " + mid);
                return;
            } else if (arr[mid] < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        System.out.println("Not Found");
    }
}
```
### c) Bubble Sort

```bash
public class BubbleSort {
    public static void main(String[] args) {
        int[] arr = {5, 3, 8, 4, 2};
        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
        for (int num : arr) System.out.print(num + " ");
    }
}
```

```bash
| Pillar            | Description                                                                                     | Python Example                              |
| ----------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------- |
| **Encapsulation** | Binding data + methods in one unit (class). Access modifiers (`_`, `__`) hide internal details. | `self.__salary` hides variable inside class |
| **Abstraction**   | Hiding complex implementation using interfaces/abstract base classes.                           | Use `abc` module in Python                  |
| **Inheritance**   | A class inherits from another to reuse code.                                                    | `class Dog(Animal):`                        |
| **Polymorphism**  | Same method behaves differently depending on object type.                                       | Method overriding, duck typing              |
```
