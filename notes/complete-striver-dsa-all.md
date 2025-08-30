# DSA

## Fundamentals

#### User Input/Output
Handle basic input and output operations.
```java
import java.util.Scanner;
public class BasicIO {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String name = sc.nextLine();
        System.out.println("Hello " + name);
        sc.close();
    }
}
```

#### Data Types
Understanding primitive and reference data types.
```java
public class DataTypes {
    public static void main(String[] args) {
        int num = 42;
        double decimal = 3.14;
        char ch = 'A';
        boolean flag = true;
        String text = "Hello";
    }
}
```

#### If Else Statements
Conditional decision making structures.
```java
public class Conditionals {
    public static String checkNumber(int n) {
        if (n > 0) return "Positive";
        else if (n < 0) return "Negative";
        else return "Zero";
    }
}
```

#### Switch Statements
Multi-way branching using switch case.
```java
public class SwitchDemo {
    public static String getDay(int day) {
        switch(day) {
            case 1: return "Monday";
            case 2: return "Tuesday";
            case 3: return "Wednesday";
            case 4: return "Thursday";
            case 5: return "Friday";
            case 6: return "Saturday";
            case 7: return "Sunday";
            default: return "Invalid";
        }
    }
}
```

#### Arrays & Strings
Basic operations on arrays and strings.
```java
public class ArraysStrings {
    public static void basicOperations() {
        int[] arr = {1, 2, 3, 4, 5};
        String str = "Hello World";
        System.out.println("Array length: " + arr.length);
        System.out.println("String length: " + str.length());
    }
}
```

#### For Loops
Iteration using for loops.
```java
public class ForLoops {
    public static void printNumbers(int n) {
        for (int i = 1; i <= n; i++) {
            System.out.print(i + " ");
        }
    }
}
```

#### While Loops
Iteration using while loops.
```java
public class WhileLoops {
    public static int factorial(int n) {
        int result = 1;
        while (n > 0) {
            result *= n--;
        }
        return result;
    }
}
```

#### Functions
Method definition and parameter passing.
```java
public class Functions {
    public static int add(int a, int b) {
        return a + b;
    }
    
    public static void modifyArray(int[] arr) {
        arr[0] = 100;
    }
}
```

### Patterns


#### Rectangular Star Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=4:**
```
* * * * 
* * * * 
* * * * 
* * * * 
```

```java
public class Pattern1 {
    public static void pattern1(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

#### Right Angled Triangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
* 
* * 
* * * 
* * * * 
* * * * * 
```

```java
public class Pattern2 {
    public static void pattern2(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

#### Inverted Right Pyramid
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
* * * * * 
* * * * 
* * * 
* * 
* 
```

```java
public class Pattern5 {
    public static void pattern5(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

#### Star Pyramid
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
    *
   ***
  *****
 *******
*********
```

```java
public class Pattern7 {
    public static void pattern7(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                System.out.print(" ");
            }
            for (int j = 0; j < 2 * i + 1; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

#### Inverted Star Pyramid
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
*********
 *******
  *****
   ***
    *
```

```java
public class Pattern8 {
    public static void pattern8(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i; j++) {
                System.out.print(" ");
            }
            for (int j = 0; j < 2 * n - (2 * i + 1); j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

#### Diamond Star Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
    *
   ***
  *****
 *******
*********
*********
 *******
  *****
   ***
    *
```

```java
public class Pattern9 {
    public static void pattern9(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                System.out.print(" ");
            }
            for (int j = 0; j < 2 * i + 1; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i; j++) {
                System.out.print(" ");
            }
            for (int j = 0; j < 2 * n - (2 * i + 1); j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

#### Half Diamond Star Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
*
**
***
****
*****
****
***
**
*
```

```java
public class Pattern10 {
    public static void pattern10(int n) {
        for (int i = 1; i <= 2 * n - 1; i++) {
            int stars = i;
            if (i > n) stars = 2 * n - i;
            for (int j = 1; j <= stars; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

#### Number Crown Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=4:**
```
1      1
12    21
123  321
12344321
```

```java
public class Pattern12 {
    public static void pattern12(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j);
            }
            for (int j = 1; j <= 2 * (n - i); j++) {
                System.out.print(" ");
            }
            for (int j = i; j >= 1; j--) {
                System.out.print(j);
            }
            System.out.println();
        }
    }
}
```

#### Alpha Hill Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=4:**
```
   A
  ABA
 ABCBA
ABCDCBA
```

```java
public class Pattern17 {
    public static void pattern17(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                System.out.print(" ");
            }
            char ch = 'A';
            int breakpoint = (2 * i + 1) / 2;
            for (int j = 1; j <= 2 * i + 1; j++) {
                System.out.print(ch);
                if (j <= breakpoint) ch++;
                else ch--;
            }
            System.out.println();
        }
    }
}
```

#### Symmetric-Void Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
**********
****  ****
***    ***
**      **
*        *
*        *
**      **
***    ***
****  ****
**********
```

```java
public class Pattern19 {
    public static void pattern19(int n) {
        int initialSpaces = 0;
        for (int i = 0; i < n; i++) {
            for (int j = 1; j <= n - i; j++) {
                System.out.print("*");
            }
            for (int j = 0; j < initialSpaces; j++) {
                System.out.print(" ");
            }
            for (int j = 1; j <= n - i; j++) {
                System.out.print("*");
            }
            initialSpaces += 2;
            System.out.println();
        }
        initialSpaces = 2 * n - 2;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            for (int j = 0; j < initialSpaces; j++) {
                System.out.print(" ");
            }
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            initialSpaces -= 2;
            System.out.println();
        }
    }
}
```

#### Butterfly Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
*        *
**      **
***    ***
****  ****
**********
****  ****
***    ***
**      **
*        *
```

```java
public class Pattern20 {
    public static void pattern20(int n) {
        int spaces = 2 * n - 2;
        for (int i = 1; i <= 2 * n - 1; i++) {
            int stars = i;
            if (i > n) stars = 2 * n - i;
            
            for (int j = 1; j <= stars; j++) {
                System.out.print("*");
            }
            for (int j = 1; j <= spaces; j++) {
                System.out.print(" ");
            }
            for (int j = 1; j <= stars; j++) {
                System.out.print("*");
            }
            System.out.println();
            
            if (i < n) spaces -= 2;
            else spaces += 2;
        }
    }
}
```

#### Hollow Rectangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=4:**
```
****
*  *
*  *
****
```

```java
public class Pattern21 {
    public static void pattern21(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 || j == 0 || i == n - 1 || j == n - 1) {
                    System.out.print("*");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println();
        }
    }
}
```

---

### Number Patterns

#### Right-Angled Number Triangle
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
1 
1 2 
1 2 3 
1 2 3 4 
1 2 3 4 5 
```

```java
public class Pattern3 {
    public static void pattern3(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }
    }
}
```

#### Right-Angled Number Triangle II
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
1 
2 2 
3 3 3 
4 4 4 4 
5 5 5 5 5 
```

```java
public class Pattern4 {
    public static void pattern4(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(i + " ");
            }
            System.out.println();
        }
    }
}
```

#### Inverted Numbered Right Pyramid
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
1 2 3 4 5 
1 2 3 4 
1 2 3 
1 2 
1 
```

```java
public class Pattern6 {
    public static void pattern6(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i + 1; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }
    }
}
```

#### Binary Number Triangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
1
01
101
0101
10101
```

```java
public class Pattern11 {
    public static void pattern11(int n) {
        int start = 1;
        for (int i = 0; i < n; i++) {
            if (i % 2 == 0) start = 1;
            else start = 0;
            for (int j = 0; j <= i; j++) {
                System.out.print(start);
                start = 1 - start;
            }
            System.out.println();
        }
    }
}
```

#### Increasing Number Triangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

```java
public class Pattern13 {
    public static void pattern13(int n) {
        int num = 1;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(num + " ");
                num++;
            }
            System.out.println();
        }
    }
}
```

#### The Number Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=4:**
```
4 4 4 4 4 4 4 
4 3 3 3 3 3 4 
4 3 2 2 2 3 4 
4 3 2 1 2 3 4 
```

```java
public class Pattern22 {
    public static void pattern22(int n) {
        for (int i = 0; i < 2 * n - 1; i++) {
            for (int j = 0; j < 2 * n - 1; j++) {
                int top = i;
                int left = j;
                int right = (2 * n - 2) - j;
                int down = (2 * n - 2) - i;
                System.out.print(n - Math.min(Math.min(top, down), Math.min(left, right)) + " ");
            }
            System.out.println();
        }
    }
}
```

---

### Character Patterns

#### Increasing Letter Triangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
A 
A B 
A B C 
A B C D 
A B C D E 
```

```java
public class Pattern14 {
    public static void pattern14(int n) {
        for (int i = 0; i < n; i++) {
            for (char ch = 'A'; ch <= 'A' + i; ch++) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }
    }
}
```

#### Reverse Letter Triangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
A B C D E 
A B C D 
A B C 
A B 
A 
```

```java
public class Pattern15 {
    public static void pattern15(int n) {
        for (int i = 0; i < n; i++) {
            for (char ch = 'A'; ch <= 'A' + (n - i - 1); ch++) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }
    }
}
```

---

### Mixed Patterns

### 16. Alpha-Ramp Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
A 
B B 
C C C 
D D D D 
E E E E E 
```

```java
public class Pattern16 {
    public static void pattern16(int n) {
        for (int i = 0; i < n; i++) {
            char ch = (char) ('A' + i);
            for (int j = 0; j <= i; j++) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }
    }
}
```

#### Alpha-Triangle Pattern
**Time:** O(n²) **Space:** O(1)

**Output for n=5:**
```
E 
D E 
C D E 
B C D E 
A B C D E 
```

```java
public class Pattern18 {
    public static void pattern18(int n) {
        for (int i = 0; i < n; i++) {
            for (char ch = (char) ('A' + n - 1 - i); ch <= (char) ('A' + n - 1); ch++) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }
    }
}
```

---

### Mathematics

#### Count Digits
Count number of digits in a number.
```java
public class CountDigits {
    public static int countDigits(int n) {
        if (n == 0) return 1;
        int count = 0;
        n = Math.abs(n);
        while (n > 0) {
            count++;
            n /= 10;
        }
        return count;
    }
}
```

#### Reverse a Number
Reverse the digits of a number.
```java
public class ReverseNumber {
    public static int reverse(int n) {
        int reversed = 0;
        boolean negative = n < 0;
        n = Math.abs(n);
        while (n > 0) {
            reversed = reversed * 10 + n % 10;
            n /= 10;
        }
        return negative ? -reversed : reversed;
    }
}
```

#### Check Palindrome
Check if a number reads same forwards and backwards.
```java
public class CheckPalindrome {
    public static boolean isPalindrome(int n) {
        if (n < 0) return false;
        int original = n;
        int reversed = 0;
        while (n > 0) {
            reversed = reversed * 10 + n % 10;
            n /= 10;
        }
        return original == reversed;
    }
}
```

#### GCD or HCF
Find Greatest Common Divisor using Euclidean algorithm.
```java
public class GCD {
    public static int findGCD(int a, int b) {
        if (b == 0) return a;
        return findGCD(b, a % b);
    }
    
    public static int findGCDIterative(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
}
```

#### Armstrong Numbers
Check if sum of cubes of digits equals the number itself.
```java
public class ArmstrongNumber {
    public static boolean isArmstrong(int n) {
        int original = n;
        int digits = String.valueOf(n).length();
        int sum = 0;
        while (n > 0) {
            int digit = n % 10;
            sum += Math.pow(digit, digits);
            n /= 10;
        }
        return sum == original;
    }
}
```

#### Print all Divisors
Find and print all divisors of a number efficiently.
```java
import java.util.*;
public class PrintDivisors {
    public static List<Integer> findDivisors(int n) {
        List<Integer> divisors = new ArrayList<>();
        for (int i = 1; i <= Math.sqrt(n); i++) {
            if (n % i == 0) {
                divisors.add(i);
                if (i != n / i) {
                    divisors.add(n / i);
                }
            }
        }
        Collections.sort(divisors);
        return divisors;
    }
}
```

#### Check for Prime
Check if a number is prime using optimized method.
```java
public class CheckPrime {
    public static boolean isPrime(int n) {
        if (n <= 1) return false;
        if (n <= 3) return true;
        if (n % 2 == 0 || n % 3 == 0) return false;
        for (int i = 5; i * i <= n; i += 6) {
            if (n % i == 0 || n % (i + 2) == 0) {
                return false;
            }
        }
        return true;
    }
}
```

### Recursion

#### Print Something N Times
Print a message N times using recursion.
```java
public class RecursivePrint {
    public static void printNTimes(String message, int n) {
        if (n <= 0) return;
        System.out.println(message);
        printNTimes(message, n - 1);
    }
}
```

#### Print Name N Times
Print name N times recursively.
```java
public class PrintName {
    public static void printName(String name, int n) {
        if (n <= 0) return;
        System.out.println(name);
        printName(name, n - 1);
    }
}
```

#### Print 1 to N
Print numbers from 1 to N using recursion.
```java
public class Print1ToN {
    public static void printNumbers(int n) {
        if (n <= 0) return;
        printNumbers(n - 1);
        System.out.print(n + " ");
    }
}
```

#### Print N to 1
Print numbers from N to 1 using recursion.
```java
public class PrintNTo1 {
    public static void printNumbers(int n) {
        if (n <= 0) return;
        System.out.print(n + " ");
        printNumbers(n - 1);
    }
}
```

#### Sum of First N Numbers
Calculate sum of first N natural numbers recursively.
```java
public class SumOfN {
    public static int sumOfN(int n) {
        if (n <= 0) return 0;
        return n + sumOfN(n - 1);
    }
}
```

#### Factorial of N Numbers
Calculate factorial using recursion.
```java
public class Factorial {
    public static long factorial(int n) {
        if (n <= 1) return 1;
        return n * factorial(n - 1);
    }
}
```

#### Reverse an Array
Reverse array elements using recursion.
```java
public class ReverseArray {
    public static void reverseArray(int[] arr, int start, int end) {
        if (start >= end) return;
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        reverseArray(arr, start + 1, end - 1);
    }
}
```

#### Check if String is Palindrome
Check palindrome using recursion.
```java
public class StringPalindrome {
    public static boolean isPalindrome(String s, int start, int end) {
        if (start >= end) return true;
        if (s.charAt(start) != s.charAt(end)) return false;
        return isPalindrome(s, start + 1, end - 1);
    }
}
```

#### Fibonacci Number
Calculate nth Fibonacci number recursively.
```java
public class Fibonacci {
    public static int fibonacci(int n) {
        if (n <= 1) return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
    
    public static int fibonacciOptimized(int n) {
        if (n <= 1) return n;
        int a = 0, b = 1;
        for (int i = 2; i <= n; i++) {
            int temp = a + b;
            a = b;
            b = temp;
        }
        return b;
    }
}
```

### Hashing

#### Hashing Theory
Basic concepts and implementation of hashing.
```java
import java.util.*;
public class HashingBasics {
    public static void demonstrateHashing() {
        Map<Integer, Integer> frequency = new HashMap<>();
        int[] arr = {1, 2, 3, 2, 1, 3, 1};
        for (int num : arr) {
            frequency.put(num, frequency.getOrDefault(num, 0) + 1);
        }
        System.out.println("Frequency map: " + frequency);
    }
}
```

#### Counting Frequencies of Array Elements
Count frequency of each element in array.
```java
import java.util.*;
public class CountFrequencies {
    public static Map<Integer, Integer> countFrequencies(int[] arr) {
        Map<Integer, Integer> frequency = new HashMap<>();
        for (int num : arr) {
            frequency.put(num, frequency.getOrDefault(num, 0) + 1);
        }
        return frequency;
    }
}
```

#### Find Highest/Lowest Frequency Element
Find elements with maximum and minimum frequency.
```java
import java.util.*;
public class FrequencyExtremes {
    public static int[] findExtremes(int[] arr) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int num : arr) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        
        int maxFreq = 0, minFreq = Integer.MAX_VALUE;
        int maxElement = arr[0], minElement = arr[0];
        
        for (Map.Entry<Integer, Integer> entry : freq.entrySet()) {
            int f = entry.getValue();
            int element = entry.getKey();
            if (f > maxFreq) {
                maxFreq = f;
                maxElement = element;
            }
            if (f < minFreq) {
                minFreq = f;
                minElement = element;
            }
        }
        return new int[]{maxElement, minElement};
    }
}
```

---

## Sorting

#### Selection Sort
Sort by repeatedly finding minimum element.
```java
public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }
}
```

#### Bubble Sort
Sort by repeatedly swapping adjacent elements.
```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            boolean swapped = false;
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            if (!swapped) break;
        }
    }
}
```

#### Insertion Sort
Sort by building sorted array one element at a time.
```java
public class InsertionSort {
    public static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }
}
```

#### Merge Sort
Divide and conquer sorting algorithm.
```java
public class MergeSort {
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);
            merge(arr, left, mid, right);
        }
    }
    
    private static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;
        int[] L = new int[n1];
        int[] R = new int[n2];
        
        for (int i = 0; i < n1; i++) L[i] = arr[left + i];
        for (int j = 0; j < n2; j++) R[j] = arr[mid + 1 + j];
        
        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }
        
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }
}
```

#### Recursive Bubble Sort
Bubble sort implemented recursively.
```java
public class RecursiveBubbleSort {
    public static void bubbleSort(int[] arr, int n) {
        if (n == 1) return;
        for (int i = 0; i < n - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                int temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
            }
        }
        bubbleSort(arr, n - 1);
    }
}
```

#### Recursive Insertion Sort
Insertion sort implemented recursively.
```java
public class RecursiveInsertionSort {
    public static void insertionSort(int[] arr, int n) {
        if (n <= 1) return;
        insertionSort(arr, n - 1);
        int last = arr[n - 1];
        int j = n - 2;
        while (j >= 0 && arr[j] > last) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = last;
    }
}
```

#### Quick Sort
Partition-based sorting algorithm.
```java
public class QuickSort {
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }
    
    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }
}
```

---

## Arrays

### 1. Largest Element in Array
**Problem:** Find the largest element in the given array.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LargestElement {
    public static int findLargest(int[] arr) {
        int max = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    }
}
```

### 2. Second Largest Element in Array
**Problem:** Find the second largest element without sorting.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class SecondLargest {
    public static int findSecondLargest(int[] arr) {
        if (arr.length < 2) return -1;
        
        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        
        for (int num : arr) {
            if (num > largest) {
                secondLargest = largest;
                largest = num;
            } else if (num > secondLargest && num != largest) {
                secondLargest = num;
            }
        }
        
        return secondLargest == Integer.MIN_VALUE ? -1 : secondLargest;
    }
}
```

### 3. Check if Array is Sorted
**Problem:** Check if the array is sorted in non-decreasing order.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class CheckSorted {
    public static boolean isSorted(int[] arr) {
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] < arr[i - 1]) {
                return false;
            }
        }
        return true;
    }
}
```

### 4. Remove Duplicates from Sorted Array
**Problem:** Remove duplicates in-place from sorted array and return new length.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class RemoveDuplicates {
    public static int removeDuplicates(int[] nums) {
        if (nums.length == 0) return 0;
        
        int j = 0;
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] != nums[j]) {
                j++;
                nums[j] = nums[i];
            }
        }
        
        return j + 1;
    }
}
```

### 5. Left Rotate Array by One Place
**Problem:** Rotate the array elements to the left by one position.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LeftRotateOne {
    public static void leftRotate(int[] arr) {
        if (arr.length <= 1) return;
        
        int temp = arr[0];
        for (int i = 1; i < arr.length; i++) {
            arr[i - 1] = arr[i];
        }
        arr[arr.length - 1] = temp;
    }
}
```

### 6. Left Rotate Array by D Places
**Problem:** Rotate the array to the left by D positions.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LeftRotateD {
    public static void leftRotate(int[] arr, int d) {
        int n = arr.length;
        d = d % n;
        
        reverse(arr, 0, d - 1);
        reverse(arr, d, n - 1);
        reverse(arr, 0, n - 1);
    }
    
    private static void reverse(int[] arr, int start, int end) {
        while (start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }
}
```

### 7. Move Zeros to End
**Problem:** Move all zeros to the end while maintaining relative order of non-zero elements.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MoveZeros {
    public static void moveZeros(int[] nums) {
        int j = 0;
        
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                nums[j++] = nums[i];
            }
        }
        
        while (j < nums.length) {
            nums[j++] = 0;
        }
    }
    
    public static void moveZerosOptimal(int[] nums) {
        int j = 0;
        
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                if (i != j) {
                    int temp = nums[i];
                    nums[i] = nums[j];
                    nums[j] = temp;
                }
                j++;
            }
        }
    }
}
```

### 8. Linear Search
**Problem:** Search for an element in the array and return its index.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LinearSearch {
    public static int search(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i;
            }
        }
        return -1;
    }
}
```

### 9. Find the Union
**Problem:** Find union of two sorted arrays.  
**Time Complexity:** O(n + m)  
**Space Complexity:** O(n + m)

```java
import java.util.*;

public class ArrayUnion {
    public static List<Integer> findUnion(int[] arr1, int[] arr2) {
        List<Integer> union = new ArrayList<>();
        int i = 0, j = 0;
        
        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] <= arr2[j]) {
                if (union.isEmpty() || union.get(union.size() - 1) != arr1[i]) {
                    union.add(arr1[i]);
                }
                i++;
            } else {
                if (union.isEmpty() || union.get(union.size() - 1) != arr2[j]) {
                    union.add(arr2[j]);
                }
                j++;
            }
        }
        
        while (i < arr1.length) {
            if (union.isEmpty() || union.get(union.size() - 1) != arr1[i]) {
                union.add(arr1[i]);
            }
            i++;
        }
        
        while (j < arr2.length) {
            if (union.isEmpty() || union.get(union.size() - 1) != arr2[j]) {
                union.add(arr2[j]);
            }
            j++;
        }
        
        return union;
    }
}
```

### 10. Find Missing Number in Array
**Problem:** Find the missing number from array containing n-1 numbers from range 1 to n.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MissingNumber {
    public static int findMissing(int[] nums) {
        int n = nums.length;
        int expectedSum = n * (n + 1) / 2;
        int actualSum = 0;
        
        for (int num : nums) {
            actualSum += num;
        }
        
        return expectedSum - actualSum;
    }
    
    public static int findMissingXOR(int[] nums) {
        int n = nums.length;
        int xor1 = 0, xor2 = 0;
        
        for (int i = 0; i < n; i++) {
            xor2 ^= nums[i];
            xor1 ^= (i + 1);
        }
        xor1 ^= (n + 1);
        
        return xor1 ^ xor2;
    }
}
```

### 11. Maximum Consecutive Ones
**Problem:** Find the maximum number of consecutive 1s in the array.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MaxConsecutiveOnes {
    public static int findMaxConsecutiveOnes(int[] nums) {
        int maxCount = 0;
        int currentCount = 0;
        
        for (int num : nums) {
            if (num == 1) {
                currentCount++;
                maxCount = Math.max(maxCount, currentCount);
            } else {
                currentCount = 0;
            }
        }
        
        return maxCount;
    }
}
```

### 12. Find Single Number
**Problem:** Find the number that appears once while every other number appears twice.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class SingleNumber {
    public static int singleNumber(int[] nums) {
        int result = 0;
        for (int num : nums) {
            result ^= num;
        }
        return result;
    }
}
```

### 13. Longest Subarray with Sum K (Positives)
**Problem:** Find longest subarray with given sum K (array contains only positives).  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LongestSubarrayPositive {
    public static int longestSubarray(int[] arr, int k) {
        int left = 0, right = 0;
        int sum = 0;
        int maxLength = 0;
        
        while (right < arr.length) {
            sum += arr[right];
            
            while (sum > k && left <= right) {
                sum -= arr[left];
                left++;
            }
            
            if (sum == k) {
                maxLength = Math.max(maxLength, right - left + 1);
            }
            
            right++;
        }
        
        return maxLength;
    }
}
```

### 14. Longest Subarray with Sum K (Positives + Negatives)
**Problem:** Find longest subarray with given sum K (array can contain negatives).  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class LongestSubarrayAll {
    public static int longestSubarray(int[] arr, int k) {
        Map<Integer, Integer> sumMap = new HashMap<>();
        int sum = 0;
        int maxLength = 0;
        
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
            
            if (sum == k) {
                maxLength = i + 1;
            }
            
            if (sumMap.containsKey(sum - k)) {
                maxLength = Math.max(maxLength, i - sumMap.get(sum - k));
            }
            
            if (!sumMap.containsKey(sum)) {
                sumMap.put(sum, i);
            }
        }
        
        return maxLength;
    }
}
```


### 15. Two Sum Problem
**Problem:** Find two numbers in array that add up to target.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }
            map.put(nums[i], i);
        }
        
        return new int[]{-1, -1};
    }
    
    public static boolean twoSumExists(int[] nums, int target) {
        Arrays.sort(nums);
        int left = 0, right = nums.length - 1;
        
        while (left < right) {
            int sum = nums[left] + nums[right];
            if (sum == target) return true;
            else if (sum < target) left++;
            else right--;
        }
        
        return false;
    }
}
```

### 16. Sort Array of 0s, 1s, and 2s (Dutch National Flag)
**Problem:** Sort array containing only 0, 1, and 2.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class Sort012 {
    public static void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;
        
        while (mid <= high) {
            if (nums[mid] == 0) {
                swap(nums, low++, mid++);
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                swap(nums, mid, high--);
            }
        }
    }
    
    private static void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```

### 17. Majority Element (>n/2 times)
**Problem:** Find element that appears more than n/2 times.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MajorityElement {
    public static int majorityElement(int[] nums) {
        int count = 0;
        int candidate = 0;
        
        for (int num : nums) {
            if (count == 0) {
                candidate = num;
            }
            count += (num == candidate) ? 1 : -1;
        }
        
        return candidate;
    }
}
```

### 18. Maximum Subarray Sum (Kadane's Algorithm)
**Problem:** Find the maximum sum of contiguous subarray.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class KadaneAlgorithm {
    public static int maxSubArray(int[] nums) {
        int maxSoFar = nums[0];
        int maxEndingHere = nums[0];
        
        for (int i = 1; i < nums.length; i++) {
            maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }
        
        return maxSoFar;
    }
    
    public static void printMaxSubarray(int[] nums) {
        int maxSoFar = nums[0];
        int maxEndingHere = nums[0];
        int start = 0, end = 0, tempStart = 0;
        
        for (int i = 1; i < nums.length; i++) {
            if (maxEndingHere < 0) {
                maxEndingHere = nums[i];
                tempStart = i;
            } else {
                maxEndingHere += nums[i];
            }
            
            if (maxSoFar < maxEndingHere) {
                maxSoFar = maxEndingHere;
                start = tempStart;
                end = i;
            }
        }
        
        System.out.print("Maximum subarray: ");
        for (int i = start; i <= end; i++) {
            System.out.print(nums[i] + " ");
        }
        System.out.println("\nSum: " + maxSoFar);
    }
}
```

### 19. Stock Buy and Sell
**Problem:** Find maximum profit from buying and selling stock once.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class StockBuySell {
    public static int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;
        
        for (int price : prices) {
            if (price < minPrice) {
                minPrice = price;
            } else if (price - minPrice > maxProfit) {
                maxProfit = price - minPrice;
            }
        }
        
        return maxProfit;
    }
}
```

### 20. Rearrange Array in Alternating Positive and Negative
**Problem:** Rearrange array so positive and negative numbers alternate.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class RearrangeArray {
    public static int[] rearrangeArray(int[] nums) {
        int[] result = new int[nums.length];
        int posIndex = 0, negIndex = 1;
        
        for (int num : nums) {
            if (num > 0) {
                result[posIndex] = num;
                posIndex += 2;
            } else {
                result[negIndex] = num;
                negIndex += 2;
            }
        }
        
        return result;
    }
    
    public static int[] rearrangeVariety2(int[] nums) {
        List<Integer> positive = new ArrayList<>();
        List<Integer> negative = new ArrayList<>();
        
        for (int num : nums) {
            if (num > 0) positive.add(num);
            else negative.add(num);
        }
        
        if (positive.size() > negative.size()) {
            for (int i = 0; i < negative.size(); i++) {
                nums[2 * i] = positive.get(i);
                nums[2 * i + 1] = negative.get(i);
            }
            int index = negative.size() * 2;
            for (int i = negative.size(); i < positive.size(); i++) {
                nums[index++] = positive.get(i);
            }
        } else {
            for (int i = 0; i < positive.size(); i++) {
                nums[2 * i] = positive.get(i);
                nums[2 * i + 1] = negative.get(i);
            }
            int index = positive.size() * 2;
            for (int i = positive.size(); i < negative.size(); i++) {
                nums[index++] = negative.get(i);
            }
        }
        
        return nums;
    }
}
```

### 21. Next Permutation
**Problem:** Find the next lexicographically greater permutation.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class NextPermutation {
    public static void nextPermutation(int[] nums) {
        int i = nums.length - 2;
        
        while (i >= 0 && nums[i] >= nums[i + 1]) {
            i--;
        }
        
        if (i >= 0) {
            int j = nums.length - 1;
            while (nums[j] <= nums[i]) {
                j--;
            }
            swap(nums, i, j);
        }
        
        reverse(nums, i + 1);
    }
    
    private static void reverse(int[] nums, int start) {
        int end = nums.length - 1;
        while (start < end) {
            swap(nums, start++, end--);
        }
    }
    
    private static void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```

### 22. Leaders in Array
**Problem:** Find all leaders (elements greater than all elements to their right).  
**Time Complexity:** O(n)  
**Space Complexity:** O(k) where k is number of leaders

```java
import java.util.*;

public class LeadersInArray {
    public static List<Integer> findLeaders(int[] arr) {
        List<Integer> leaders = new ArrayList<>();
        int n = arr.length;
        int maxFromRight = arr[n - 1];
        leaders.add(maxFromRight);
        
        for (int i = n - 2; i >= 0; i--) {
            if (arr[i] > maxFromRight) {
                maxFromRight = arr[i];
                leaders.add(maxFromRight);
            }
        }
        
        Collections.reverse(leaders);
        return leaders;
    }
}
```

### 23. Longest Consecutive Sequence
**Problem:** Find length of longest consecutive elements sequence.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class LongestConsecutive {
    public static int longestConsecutive(int[] nums) {
        Set<Integer> numSet = new HashSet<>();
        for (int num : nums) {
            numSet.add(num);
        }
        
        int longestStreak = 0;
        
        for (int num : numSet) {
            if (!numSet.contains(num - 1)) {
                int currentNum = num;
                int currentStreak = 1;
                
                while (numSet.contains(currentNum + 1)) {
                    currentNum++;
                    currentStreak++;
                }
                
                longestStreak = Math.max(longestStreak, currentStreak);
            }
        }
        
        return longestStreak;
    }
}
```

### 24. Set Matrix Zeros
**Problem:** Set entire row and column to zero if element is zero.  
**Time Complexity:** O(m * n)  
**Space Complexity:** O(1)

```java
public class SetMatrixZeros {
    public static void setZeroes(int[][] matrix) {
        int m = matrix.length;
        int n = matrix[0].length;
        boolean firstRowZero = false;
        boolean firstColZero = false;
        
        for (int i = 0; i < m; i++) {
            if (matrix[i][0] == 0) {
                firstColZero = true;
                break;
            }
        }
        
        for (int j = 0; j < n; j++) {
            if (matrix[0][j] == 0) {
                firstRowZero = true;
                break;
            }
        }
        
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (matrix[i][j] == 0) {
                    matrix[i][0] = 0;
                    matrix[0][j] = 0;
                }
            }
        }
        
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                    matrix[i][j] = 0;
                }
            }
        }
        
        if (firstRowZero) {
            for (int j = 0; j < n; j++) {
                matrix[0][j] = 0;
            }
        }
        
        if (firstColZero) {
            for (int i = 0; i < m; i++) {
                matrix[i][0] = 0;
            }
        }
    }
}
```

### 25. Rotate Matrix by 90 Degrees
**Problem:** Rotate n×n matrix clockwise by 90 degrees in-place.  
**Time Complexity:** O(n²)  
**Space Complexity:** O(1)

```java
public class RotateMatrix {
    public static void rotate(int[][] matrix) {
        int n = matrix.length;
        
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = temp;
            }
        }
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n / 2; j++) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[i][n - 1 - j];
                matrix[i][n - 1 - j] = temp;
            }
        }
    }
}
```

### 26. Spiral Traversal of Matrix
**Problem:** Return elements of matrix in spiral order.  
**Time Complexity:** O(m * n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class SpiralMatrix {
    public static List<Integer> spiralOrder(int[][] matrix) {
        List<Integer> result = new ArrayList<>();
        if (matrix.length == 0) return result;
        
        int top = 0, bottom = matrix.length - 1;
        int left = 0, right = matrix[0].length - 1;
        
        while (top <= bottom && left <= right) {
            for (int j = left; j <= right; j++) {
                result.add(matrix[top][j]);
            }
            top++;
            
            for (int i = top; i <= bottom; i++) {
                result.add(matrix[i][right]);
            }
            right--;
            
            if (top <= bottom) {
                for (int j = right; j >= left; j--) {
                    result.add(matrix[bottom][j]);
                }
                bottom--;
            }
            
            if (left <= right) {
                for (int i = bottom; i >= top; i--) {
                    result.add(matrix[i][left]);
                }
                left++;
            }
        }
        
        return result;
    }
}
```

### 27. Count Subarrays with Given Sum
**Problem:** Count number of subarrays with sum equal to k.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class SubarraySum {
    public static int subarraySum(int[] nums, int k) {
        Map<Integer, Integer> sumCount = new HashMap<>();
        sumCount.put(0, 1);
        
        int sum = 0;
        int count = 0;
        
        for (int num : nums) {
            sum += num;
            if (sumCount.containsKey(sum - k)) {
                count += sumCount.get(sum - k);
            }
            sumCount.put(sum, sumCount.getOrDefault(sum, 0) + 1);
        }
        
        return count;
    }
}
```


### 28. Pascal's Triangle
**Problem:** Generate first numRows of Pascal's triangle.  
**Time Complexity:** O(numRows²)  
**Space Complexity:** O(numRows²)

```java
import java.util.*;

public class PascalTriangle {
    public static List<List<Integer>> generate(int numRows) {
        List<List<Integer>> triangle = new ArrayList<>();
        
        for (int i = 0; i < numRows; i++) {
            List<Integer> row = new ArrayList<>();
            for (int j = 0; j <= i; j++) {
                if (j == 0 || j == i) {
                    row.add(1);
                } else {
                    row.add(triangle.get(i - 1).get(j - 1) + triangle.get(i - 1).get(j));
                }
            }
            triangle.add(row);
        }
        
        return triangle;
    }
    
    public static List<Integer> getRow(int rowIndex) {
        List<Integer> row = new ArrayList<>();
        for (int i = 0; i <= rowIndex; i++) {
            row.add(nCr(rowIndex, i));
        }
        return row;
    }
    
    private static int nCr(int n, int r) {
        long result = 1;
        for (int i = 0; i < r; i++) {
            result = result * (n - i) / (i + 1);
        }
        return (int) result;
    }
    
    public static int pascalElement(int row, int col) {
        return nCr(row, col);
    }
}
```

### 29. Majority Element (>n/3 times)
**Problem:** Find all elements appearing more than ⌊n/3⌋ times.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class MajorityElementII {
    public static List<Integer> majorityElement(int[] nums) {
        List<Integer> result = new ArrayList<>();
        int count1 = 0, count2 = 0;
        int candidate1 = 0, candidate2 = 1;
        
        for (int num : nums) {
            if (num == candidate1) {
                count1++;
            } else if (num == candidate2) {
                count2++;
            } else if (count1 == 0) {
                candidate1 = num;
                count1 = 1;
            } else if (count2 == 0) {
                candidate2 = num;
                count2 = 1;
            } else {
                count1--;
                count2--;
            }
        }
        
        count1 = count2 = 0;
        for (int num : nums) {
            if (num == candidate1) count1++;
            else if (num == candidate2) count2++;
        }
        
        if (count1 > nums.length / 3) result.add(candidate1);
        if (count2 > nums.length / 3) result.add(candidate2);
        
        return result;
    }
}
```

### 30. Three Sum Problem
**Problem:** Find all unique triplets that sum to zero.  
**Time Complexity:** O(n²)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class ThreeSum {
    public static List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);
        
        for (int i = 0; i < nums.length - 2; i++) {
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            
            int left = i + 1;
            int right = nums.length - 1;
            
            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];
                
                if (sum == 0) {
                    result.add(Arrays.asList(nums[i], nums[left], nums[right]));
                    
                    while (left < right && nums[left] == nums[left + 1]) left++;
                    while (left < right && nums[right] == nums[right - 1]) right--;
                    
                    left++;
                    right--;
                } else if (sum < 0) {
                    left++;
                } else {
                    right--;
                }
            }
        }
        
        return result;
    }
}
```

### 31. Four Sum Problem
**Problem:** Find all unique quadruplets that sum to target.  
**Time Complexity:** O(n³)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class FourSum {
    public static List<List<Integer>> fourSum(int[] nums, int target) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);
        
        for (int i = 0; i < nums.length - 3; i++) {
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            
            for (int j = i + 1; j < nums.length - 2; j++) {
                if (j > i + 1 && nums[j] == nums[j - 1]) continue;
                
                int left = j + 1;
                int right = nums.length - 1;
                
                while (left < right) {
                    long sum = (long)nums[i] + nums[j] + nums[left] + nums[right];
                    
                    if (sum == target) {
                        result.add(Arrays.asList(nums[i], nums[j], nums[left], nums[right]));
                        
                        while (left < right && nums[left] == nums[left + 1]) left++;
                        while (left < right && nums[right] == nums[right - 1]) right--;
                        
                        left++;
                        right--;
                    } else if (sum < target) {
                        left++;
                    } else {
                        right--;
                    }
                }
            }
        }
        
        return result;
    }
}
```

### 32. Number of Subarrays with XOR K
**Problem:** Count subarrays with XOR equal to k.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class SubarrayXOR {
    public static int subarraysWithXORK(int[] arr, int k) {
        Map<Integer, Integer> xorCount = new HashMap<>();
        xorCount.put(0, 1);
        
        int xor = 0;
        int count = 0;
        
        for (int num : arr) {
            xor ^= num;
            
            if (xorCount.containsKey(xor ^ k)) {
                count += xorCount.get(xor ^ k);
            }
            
            xorCount.put(xor, xorCount.getOrDefault(xor, 0) + 1);
        }
        
        return count;
    }
}
```

### 33. Merge Overlapping Intervals
**Problem:** Merge all overlapping intervals.  
**Time Complexity:** O(n log n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class MergeIntervals {
    public static int[][] merge(int[][] intervals) {
        if (intervals.length <= 1) return intervals;
        
        Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
        
        List<int[]> merged = new ArrayList<>();
        int[] currentInterval = intervals[0];
        merged.add(currentInterval);
        
        for (int[] interval : intervals) {
            int currentEnd = currentInterval[1];
            int nextStart = interval[0];
            int nextEnd = interval[1];
            
            if (currentEnd >= nextStart) {
                currentInterval[1] = Math.max(currentEnd, nextEnd);
            } else {
                currentInterval = interval;
                merged.add(currentInterval);
            }
        }
        
        return merged.toArray(new int[merged.size()][]);
    }
}
```

### 34. Merge Two Sorted Arrays Without Extra Space
**Problem:** Merge two sorted arrays in-place.  
**Time Complexity:** O((n+m) log(n+m))  
**Space Complexity:** O(1)

```java
public class MergeSortedArrays {
    public static void merge(int[] arr1, int[] arr2) {
        int i = arr1.length - 1;
        int j = 0;
        
        while (i >= 0 && j < arr2.length && arr1[i] > arr2[j]) {
            int temp = arr1[i];
            arr1[i] = arr2[j];
            arr2[j] = temp;
            i--;
            j++;
        }
        
        Arrays.sort(arr1);
        Arrays.sort(arr2);
    }
    
    public static void mergeOptimal(int[] arr1, int[] arr2) {
        int n = arr1.length;
        int m = arr2.length;
        int gap = (n + m + 1) / 2;
        
        while (gap > 0) {
            int i = 0;
            int j = gap;
            
            while (j < n + m) {
                if (j < n && arr1[i] > arr1[j]) {
                    swap(arr1, i, arr1, j);
                } else if (j >= n && i < n && arr1[i] > arr2[j - n]) {
                    swapArrays(arr1, i, arr2, j - n);
                } else if (i >= n && arr2[i - n] > arr2[j - n]) {
                    swap(arr2, i - n, arr2, j - n);
                }
                i++;
                j++;
            }
            
            if (gap == 1) break;
            gap = (gap + 1) / 2;
        }
    }
    
    private static void swap(int[] arr1, int i, int[] arr2, int j) {
        int temp = arr1[i];
        arr1[i] = arr2[j];
        arr2[j] = temp;
    }
    
    private static void swapArrays(int[] arr1, int i, int[] arr2, int j) {
        int temp = arr1[i];
        arr1[i] = arr2[j];
        arr2[j] = temp;
    }
}
```

### 35. Find Repeating and Missing Number
**Problem:** Find one repeating and one missing number in array.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class RepeatingMissing {
    public static int[] findNumbers(int[] arr) {
        long n = arr.length;
        long sum = (n * (n + 1)) / 2;
        long sumSquares = (n * (n + 1) * (2 * n + 1)) / 6;
        
        long actualSum = 0;
        long actualSumSquares = 0;
        
        for (int num : arr) {
            actualSum += num;
            actualSumSquares += (long)num * num;
        }
        
        long diffSum = actualSum - sum;
        long diffSumSquares = actualSumSquares - sumSquares;
        
        long sumXY = diffSumSquares / diffSum;
        
        int repeating = (int)(diffSum + sumXY) / 2;
        int missing = (int)(sumXY - repeating);
        
        return new int[]{repeating, missing};
    }
    
    public static int[] findNumbersXOR(int[] arr) {
        int xor = 0;
        int n = arr.length;
        
        for (int num : arr) {
            xor ^= num;
        }
        
        for (int i = 1; i <= n; i++) {
            xor ^= i;
        }
        
        int setBit = xor & -xor;
        int x = 0, y = 0;
        
        for (int num : arr) {
            if ((num & setBit) != 0) {
                x ^= num;
            } else {
                y ^= num;
            }
        }
        
        for (int i = 1; i <= n; i++) {
            if ((i & setBit) != 0) {
                x ^= i;
            } else {
                y ^= i;
            }
        }
        
        int count = 0;
        for (int num : arr) {
            if (num == x) count++;
        }
        
        if (count == 0) {
            return new int[]{y, x};
        }
        return new int[]{x, y};
    }
}
```

### 36. Count Inversions
**Problem:** Count pairs (i, j) such that i < j and arr[i] > arr[j].  
**Time Complexity:** O(n log n)  
**Space Complexity:** O(n)

```java
public class CountInversions {
    private static int mergeAndCount(int[] arr, int[] temp, int left, int mid, int right) {
        int i = left, j = mid, k = left;
        int invCount = 0;
        
        while (i <= mid - 1 && j <= right) {
            if (arr[i] <= arr[j]) {
                temp[k++] = arr[i++];
            } else {
                temp[k++] = arr[j++];
                invCount += (mid - i);
            }
        }
        
        while (i <= mid - 1) temp[k++] = arr[i++];
        while (j <= right) temp[k++] = arr[j++];
        
        for (i = left; i <= right; i++) {
            arr[i] = temp[i];
        }
        
        return invCount;
    }
    
    private static int mergeSortAndCount(int[] arr, int[] temp, int left, int right) {
        int invCount = 0;
        if (left < right) {
            int mid = (left + right) / 2;
            
            invCount += mergeSortAndCount(arr, temp, left, mid);
            invCount += mergeSortAndCount(arr, temp, mid + 1, right);
            invCount += mergeAndCount(arr, temp, left, mid + 1, right);
        }
        return invCount;
    }
    
    public static int countInversions(int[] arr) {
        int[] temp = new int[arr.length];
        return mergeSortAndCount(arr, temp, 0, arr.length - 1);
    }
}
```

### 37. Reverse Pairs
**Problem:** Count pairs (i, j) such that i < j and arr[i] > 2 * arr[j].  
**Time Complexity:** O(n log n)  
**Space Complexity:** O(n)

```java
public class ReversePairs {
    private static int mergeAndCount(int[] nums, int left, int mid, int right) {
        int count = 0;
        int j = mid + 1;
        
        for (int i = left; i <= mid; i++) {
            while (j <= right && nums[i] > 2L * nums[j]) {
                j++;
            }
            count += (j - (mid + 1));
        }
        
        int[] temp = new int[right - left + 1];
        int i = left, k = 0;
        j = mid + 1;
        
        while (i <= mid && j <= right) {
            if (nums[i] <= nums[j]) {
                temp[k++] = nums[i++];
            } else {
                temp[k++] = nums[j++];
            }
        }
        
        while (i <= mid) temp[k++] = nums[i++];
        while (j <= right) temp[k++] = nums[j++];
        
        for (i = left; i <= right; i++) {
            nums[i] = temp[i - left];
        }
        
        return count;
    }
    
    private static int mergeSortAndCount(int[] nums, int left, int right) {
        if (left >= right) return 0;
        
        int mid = (left + right) / 2;
        int count = mergeSortAndCount(nums, left, mid);
        count += mergeSortAndCount(nums, mid + 1, right);
        count += mergeAndCount(nums, left, mid, right);
        
        return count;
    }
    
    public static int reversePairs(int[] nums) {
        return mergeSortAndCount(nums, 0, nums.length - 1);
    }
}
```

### 38. Maximum Product Subarray
**Problem:** Find maximum product of contiguous subarray.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MaxProductSubarray {
    public static int maxProduct(int[] nums) {
        int maxSoFar = nums[0];
        int minSoFar = nums[0];
        int result = maxSoFar;
        
        for (int i = 1; i < nums.length; i++) {
            int curr = nums[i];
            int tempMax = Math.max(curr, Math.max(maxSoFar * curr, minSoFar * curr));
            minSoFar = Math.min(curr, Math.min(maxSoFar * curr, minSoFar * curr));
            
            maxSoFar = tempMax;
            result = Math.max(result, maxSoFar);
        }
        
        return result;
    }
    
    public static int maxProductOptimal(int[] nums) {
        int prefix = 1, suffix = 1;
        int maxProduct = Integer.MIN_VALUE;
        int n = nums.length;
        
        for (int i = 0; i < n; i++) {
            if (prefix == 0) prefix = 1;
            if (suffix == 0) suffix = 1;
            
            prefix *= nums[i];
            suffix *= nums[n - i - 1];
            
            maxProduct = Math.max(maxProduct, Math.max(prefix, suffix));
        }
        
        return maxProduct;
    }
}
```

---



## Binary Search

### 1. Binary Search to Find X in Sorted Array
**Problem:** Find target element in sorted array.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class BinarySearch {
    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return -1;
    }
    
    public static int binarySearchRecursive(int[] arr, int target, int left, int right) {
        if (left > right) return -1;
        
        int mid = left + (right - left) / 2;
        
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) return binarySearchRecursive(arr, target, mid + 1, right);
        else return binarySearchRecursive(arr, target, left, mid - 1);
    }
}
```

### 2. Implement Lower Bound
**Problem:** Find first occurrence >= x (lower bound).  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class LowerBound {
    public static int lowerBound(int[] arr, int x) {
        int left = 0;
        int right = arr.length;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] < x) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        return left;
    }
    
    public static int lowerBoundAlternative(int[] arr, int x) {
        int left = 0;
        int right = arr.length - 1;
        int ans = arr.length;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] >= x) {
                ans = mid;
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        
        return ans;
    }
}
```

### 3. Implement Upper Bound
**Problem:** Find first occurrence > x (upper bound).  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class UpperBound {
    public static int upperBound(int[] arr, int x) {
        int left = 0;
        int right = arr.length;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] <= x) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        return left;
    }
    
    public static int upperBoundAlternative(int[] arr, int x) {
        int left = 0;
        int right = arr.length - 1;
        int ans = arr.length;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] > x) {
                ans = mid;
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        
        return ans;
    }
}
```

### 4. Search Insert Position
**Problem:** Find position to insert target to maintain sorted order.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class SearchInsertPosition {
    public static int searchInsert(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                return mid;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return left;
    }
    
    public static int searchInsertLowerBound(int[] nums, int target) {
        return lowerBound(nums, target);
    }
    
    private static int lowerBound(int[] arr, int x) {
        int left = 0;
        int right = arr.length;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (arr[mid] < x) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        return left;
    }
}
```

### 5. Floor/Ceil in Sorted Array
**Problem:** Find floor (largest <= x) and ceil (smallest >= x).  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class FloorCeil {
    public static int[] floorCeil(int[] arr, int x) {
        int floor = findFloor(arr, x);
        int ceil = findCeil(arr, x);
        return new int[]{floor, ceil};
    }
    
    private static int findFloor(int[] arr, int x) {
        int left = 0;
        int right = arr.length - 1;
        int floor = -1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] <= x) {
                floor = arr[mid];
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return floor;
    }
    
    private static int findCeil(int[] arr, int x) {
        int left = 0;
        int right = arr.length - 1;
        int ceil = -1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] >= x) {
                ceil = arr[mid];
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        
        return ceil;
    }
}
```

### 6. Find First or Last Occurrence
**Problem:** Find first and last occurrence of target in sorted array.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class FirstLastOccurrence {
    public static int[] searchRange(int[] nums, int target) {
        int first = findFirst(nums, target);
        int last = findLast(nums, target);
        return new int[]{first, last};
    }
    
    private static int findFirst(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        int first = -1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                first = mid;
                right = mid - 1;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return first;
    }
    
    private static int findLast(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        int last = -1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                last = mid;
                left = mid + 1;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return last;
    }
}
```

### 7. Count Occurrences of Number
**Problem:** Count occurrences of target in sorted array with duplicates.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class CountOccurrences {
    public static int countOccurrences(int[] nums, int target) {
        int first = findFirst(nums, target);
        if (first == -1) return 0;
        
        int last = findLast(nums, target);
        return last - first + 1;
    }
    
    private static int findFirst(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        int first = -1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                first = mid;
                right = mid - 1;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return first;
    }
    
    private static int findLast(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        int last = -1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                last = mid;
                left = mid + 1;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return last;
    }
}
```

### 8. Find Peak Element
**Problem:** Find any peak element where nums[i-1] < nums[i] > nums[i+1].  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class FindPeakElement {
    public static int findPeakElement(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] > nums[mid + 1]) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    public static int findPeakElementAlternative(int[] nums) {
        int n = nums.length;
        
        if (n == 1) return 0;
        if (nums[0] > nums[1]) return 0;
        if (nums[n - 1] > nums[n - 2]) return n - 1;
        
        int left = 1;
        int right = n - 2;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] > nums[mid - 1] && nums[mid] > nums[mid + 1]) {
                return mid;
            }
            
            if (nums[mid] < nums[mid + 1]) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return -1;
    }
}
```

### 9. Search in Rotated Sorted Array I
**Problem:** Search target in rotated sorted array (no duplicates).  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class SearchRotatedArray {
    public static int search(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                return mid;
            }
            
            if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) {
                    right = mid - 1;
                } else {
                    left = mid + 1;
                }
            } else {
                if (nums[mid] < target && target <= nums[right]) {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }
            }
        }
        
        return -1;
    }
}
```

### 10. Search in Rotated Sorted Array II
**Problem:** Search target in rotated sorted array (with duplicates).  
**Time Complexity:** O(log n) average, O(n) worst case  
**Space Complexity:** O(1)

```java
public class SearchRotatedArrayII {
    public static boolean search(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] == target) {
                return true;
            }
            
            if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
                left++;
                right--;
            } else if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) {
                    right = mid - 1;
                } else {
                    left = mid + 1;
                }
            } else {
                if (nums[mid] < target && target <= nums[right]) {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }
            }
        }
        
        return false;
    }
}
```

### 11. Find Minimum in Rotated Sorted Array
**Problem:** Find minimum element in rotated sorted array.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class FindMinimumRotated {
    public static int findMin(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] > nums[right]) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        return nums[left];
    }
    
    public static int findMinWithDuplicates(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] > nums[right]) {
                left = mid + 1;
            } else if (nums[mid] < nums[right]) {
                right = mid;
            } else {
                right--;
            }
        }
        
        return nums[left];
    }
}
```

### 12. Find How Many Times Array Has Been Rotated
**Problem:** Find number of rotations in rotated sorted array.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class CountRotations {
    public static int countRotations(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] > nums[right]) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        return left;
    }
    
    public static int countRotationsWithDuplicates(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] > nums[right]) {
                left = mid + 1;
            } else if (nums[mid] < nums[right]) {
                right = mid;
            } else {
                right--;
            }
        }
        
        return left;
    }
}
```

### 13. Single Element in Sorted Array
**Problem:** Find single element in sorted array where every other element appears twice.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class SingleElementSorted {
    public static int singleNonDuplicate(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (mid % 2 == 1) {
                mid--;
            }
            
            if (nums[mid] != nums[mid + 1]) {
                right = mid;
            } else {
                left = mid + 2;
            }
        }
        
        return nums[left];
    }
    
    public static int singleNonDuplicateAlternative(int[] nums) {
        int left = 1;
        int right = nums.length - 2;
        
        if (nums.length == 1) return nums[0];
        if (nums[0] != nums[1]) return nums[0];
        if (nums[nums.length - 1] != nums[nums.length - 2]) return nums[nums.length - 1];
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (nums[mid] != nums[mid + 1] && nums[mid] != nums[mid - 1]) {
                return nums[mid];
            }
            
            if ((mid % 2 == 1 && nums[mid] == nums[mid - 1]) || 
                (mid % 2 == 0 && nums[mid] == nums[mid + 1])) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return -1;
    }
}
```



### 14. Find Row with Maximum Number of 1s
**Problem:** Find row with maximum 1s in binary matrix.  
**Time Complexity:** O(m + n)  
**Space Complexity:** O(1)

```java
public class MaxOnesRow {
    public static int rowWithMax1s(int[][] arr) {
        int m = arr.length;
        int n = arr[0].length;
        int maxRowIndex = -1;
        int j = n - 1;
        
        for (int i = 0; i < m; i++) {
            while (j >= 0 && arr[i][j] == 1) {
                j--;
                maxRowIndex = i;
            }
        }
        
        return maxRowIndex;
    }
    
    public static int rowWithMax1sBinarySearch(int[][] arr) {
        int m = arr.length;
        int maxCount = 0;
        int maxRowIndex = -1;
        
        for (int i = 0; i < m; i++) {
            int count = countOnes(arr[i]);
            if (count > maxCount) {
                maxCount = count;
                maxRowIndex = i;
            }
        }
        
        return maxRowIndex;
    }
    
    private static int countOnes(int[] row) {
        int left = 0;
        int right = row.length - 1;
        int firstOne = row.length;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (row[mid] == 1) {
                firstOne = mid;
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        
        return row.length - firstOne;
    }
}
```

### 15. Search in 2D Matrix
**Problem:** Search target in 2D matrix where each row is sorted.  
**Time Complexity:** O(log(m*n))  
**Space Complexity:** O(1)

```java
public class Search2DMatrix {
    public static boolean searchMatrix(int[][] matrix, int target) {
        int m = matrix.length;
        int n = matrix[0].length;
        int left = 0;
        int right = m * n - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int row = mid / n;
            int col = mid % n;
            int midValue = matrix[row][col];
            
            if (midValue == target) {
                return true;
            } else if (midValue < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return false;
    }
    
    public static boolean searchMatrixAlternative(int[][] matrix, int target) {
        int m = matrix.length;
        int n = matrix[0].length;
        int row = 0;
        int col = n - 1;
        
        while (row < m && col >= 0) {
            if (matrix[row][col] == target) {
                return true;
            } else if (matrix[row][col] > target) {
                col--;
            } else {
                row++;
            }
        }
        
        return false;
    }
}
```

### 16. Search in 2D Matrix II
**Problem:** Search target in 2D matrix where rows and columns are sorted.  
**Time Complexity:** O(m + n)  
**Space Complexity:** O(1)

```java
public class Search2DMatrixII {
    public static boolean searchMatrix(int[][] matrix, int target) {
        int m = matrix.length;
        int n = matrix[0].length;
        int row = 0;
        int col = n - 1;
        
        while (row < m && col >= 0) {
            if (matrix[row][col] == target) {
                return true;
            } else if (matrix[row][col] > target) {
                col--;
            } else {
                row++;
            }
        }
        
        return false;
    }
    
    public static boolean searchMatrixDivideConquer(int[][] matrix, int target) {
        return searchHelper(matrix, target, 0, 0, matrix.length - 1, matrix[0].length - 1);
    }
    
    private static boolean searchHelper(int[][] matrix, int target, int row1, int col1, int row2, int col2) {
        if (row1 > row2 || col1 > col2) return false;
        
        int midRow = row1 + (row2 - row1) / 2;
        int midCol = col1 + (col2 - col1) / 2;
        
        if (matrix[midRow][midCol] == target) {
            return true;
        } else if (matrix[midRow][midCol] < target) {
            return searchHelper(matrix, target, row1, midCol + 1, midRow, col2) ||
                   searchHelper(matrix, target, midRow + 1, col1, row2, col2);
        } else {
            return searchHelper(matrix, target, row1, col1, midRow - 1, col2) ||
                   searchHelper(matrix, target, midRow, col1, row2, midCol - 1);
        }
    }
}
```

### 17. Find Peak Element in 2D Matrix
**Problem:** Find peak element in 2D matrix.  
**Time Complexity:** O(n log m)  
**Space Complexity:** O(1)

```java
public class Peak2DMatrix {
    public static int[] findPeakGrid(int[][] mat) {
        int m = mat.length;
        int n = mat[0].length;
        int left = 0;
        int right = n - 1;
        
        while (left <= right) {
            int midCol = left + (right - left) / 2;
            int maxRowIndex = findMaxRow(mat, midCol);
            
            int leftVal = midCol - 1 >= 0 ? mat[maxRowIndex][midCol - 1] : -1;
            int rightVal = midCol + 1 < n ? mat[maxRowIndex][midCol + 1] : -1;
            
            if (mat[maxRowIndex][midCol] > leftVal && mat[maxRowIndex][midCol] > rightVal) {
                return new int[]{maxRowIndex, midCol};
            } else if (mat[maxRowIndex][midCol] < leftVal) {
                right = midCol - 1;
            } else {
                left = midCol + 1;
            }
        }
        
        return new int[]{-1, -1};
    }
    
    private static int findMaxRow(int[][] mat, int col) {
        int maxIndex = 0;
        for (int i = 1; i < mat.length; i++) {
            if (mat[i][col] > mat[maxIndex][col]) {
                maxIndex = i;
            }
        }
        return maxIndex;
    }
}
```

### 18. Matrix Median
**Problem:** Find median of elements in sorted matrix.  
**Time Complexity:** O(32 * m * log n)  
**Space Complexity:** O(1)

```java
public class MatrixMedian {
    public static int findMedian(int[][] matrix) {
        int m = matrix.length;
        int n = matrix[0].length;
        int low = Integer.MAX_VALUE;
        int high = Integer.MIN_VALUE;
        
        for (int i = 0; i < m; i++) {
            low = Math.min(low, matrix[i][0]);
            high = Math.max(high, matrix[i][n - 1]);
        }
        
        int required = (m * n) / 2;
        
        while (low <= high) {
            int mid = low + (high - low) / 2;
            int smallerEqual = countSmallerEqual(matrix, mid);
            
            if (smallerEqual <= required) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        
        return low;
    }
    
    private static int countSmallerEqual(int[][] matrix, int x) {
        int count = 0;
        for (int i = 0; i < matrix.length; i++) {
            count += upperBound(matrix[i], x);
        }
        return count;
    }
    
    private static int upperBound(int[] arr, int x) {
        int left = 0;
        int right = arr.length;
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (arr[mid] <= x) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        return left;
    }
}
```

### 19. Find Square Root of Number
**Problem:** Find integer square root using binary search.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class SquareRoot {
    public static int mySqrt(int x) {
        if (x == 0) return 0;
        
        int left = 1;
        int right = x;
        int result = 0;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (mid <= x / mid) {
                result = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return result;
    }
    
    public static int mySqrtAlternative(int x) {
        if (x < 2) return x;
        
        int left = 2;
        int right = x / 2;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            long num = (long) mid * mid;
            
            if (num == x) return mid;
            else if (num < x) left = mid + 1;
            else right = mid - 1;
        }
        
        return right;
    }
}
```

### 20. Find Nth Root of Number
**Problem:** Find nth root of number using binary search.  
**Time Complexity:** O(log m * log n) where m is the number  
**Space Complexity:** O(1)

```java
public class NthRoot {
    public static int nthRoot(int n, int m) {
        int left = 1;
        int right = m;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int midPowN = power(mid, n, m);
            
            if (midPowN == 1) {
                return mid;
            } else if (midPowN == 0) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return -1;
    }
    
    private static int power(int mid, int n, int m) {
        long ans = 1;
        for (int i = 1; i <= n; i++) {
            ans = ans * mid;
            if (ans > m) return 2;
        }
        if (ans == m) return 1;
        return 0;
    }
    
    public static double nthRootPrecise(int n, int m) {
        double low = 1;
        double high = m;
        double eps = 1e-6;
        
        while ((high - low) > eps) {
            double mid = (low + high) / 2.0;
            if (multiply(mid, n) < m) {
                low = mid;
            } else {
                high = mid;
            }
        }
        
        return low;
    }
    
    private static double multiply(double number, int n) {
        double ans = 1.0;
        for (int i = 1; i <= n; i++) {
            ans = ans * number;
        }
        return ans;
    }
}
```

### 21. Koko Eating Bananas
**Problem:** Find minimum eating speed to finish all bananas within h hours.  
**Time Complexity:** O(n log max_pile)  
**Space Complexity:** O(1)

```java
public class KokoEatingBananas {
    public static int minEatingSpeed(int[] piles, int h) {
        int left = 1;
        int right = getMax(piles);
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (canFinish(piles, mid, h)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    private static boolean canFinish(int[] piles, int speed, int h) {
        int hours = 0;
        for (int pile : piles) {
            hours += (pile + speed - 1) / speed;
        }
        return hours <= h;
    }
    
    private static int getMax(int[] piles) {
        int max = piles[0];
        for (int pile : piles) {
            max = Math.max(max, pile);
        }
        return max;
    }
}
```

### 22. Minimum Days to Make M Bouquets
**Problem:** Find minimum days to make m bouquets with k adjacent flowers each.  
**Time Complexity:** O(n log max_day)  
**Space Complexity:** O(1)

```java
public class MinDaysBouquets {
    public static int minDays(int[] bloomDay, int m, int k) {
        if (m * k > bloomDay.length) return -1;
        
        int left = getMin(bloomDay);
        int right = getMax(bloomDay);
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (canMakeBouquets(bloomDay, mid, m, k)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    private static boolean canMakeBouquets(int[] bloomDay, int day, int m, int k) {
        int bouquets = 0;
        int consecutive = 0;
        
        for (int bloom : bloomDay) {
            if (bloom <= day) {
                consecutive++;
                if (consecutive == k) {
                    bouquets++;
                    consecutive = 0;
                }
            } else {
                consecutive = 0;
            }
        }
        
        return bouquets >= m;
    }
    
    private static int getMin(int[] arr) {
        int min = arr[0];
        for (int num : arr) {
            min = Math.min(min, num);
        }
        return min;
    }
    
    private static int getMax(int[] arr) {
        int max = arr[0];
        for (int num : arr) {
            max = Math.max(max, num);
        }
        return max;
    }
}
```

### 23. Find Smallest Divisor
**Problem:** Find smallest divisor such that result of division is <= threshold.  
**Time Complexity:** O(n log max_num)  
**Space Complexity:** O(1)

```java
public class SmallestDivisor {
    public static int smallestDivisor(int[] nums, int threshold) {
        int left = 1;
        int right = getMax(nums);
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (getDivisionSum(nums, mid) <= threshold) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    private static int getDivisionSum(int[] nums, int divisor) {
        int sum = 0;
        for (int num : nums) {
            sum += (num + divisor - 1) / divisor;
        }
        return sum;
    }
    
    private static int getMax(int[] nums) {
        int max = nums[0];
        for (int num : nums) {
            max = Math.max(max, num);
        }
        return max;
    }
}
```

### 24. Capacity to Ship Packages within D Days
**Problem:** Find minimum ship capacity to ship all packages within D days.  
**Time Complexity:** O(n log sum)  
**Space Complexity:** O(1)

```java
public class ShipPackages {
    public static int shipWithinDays(int[] weights, int days) {
        int left = getMax(weights);
        int right = getSum(weights);
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (canShip(weights, mid, days)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    private static boolean canShip(int[] weights, int capacity, int days) {
        int daysNeeded = 1;
        int currentWeight = 0;
        
        for (int weight : weights) {
            if (currentWeight + weight > capacity) {
                daysNeeded++;
                currentWeight = weight;
            } else {
                currentWeight += weight;
            }
        }
        
        return daysNeeded <= days;
    }
    
    private static int getMax(int[] weights) {
        int max = weights[0];
        for (int weight : weights) {
            max = Math.max(max, weight);
        }
        return max;
    }
    
    private static int getSum(int[] weights) {
        int sum = 0;
        for (int weight : weights) {
            sum += weight;
        }
        return sum;
    }
}
```

### 25. Kth Missing Positive Number
**Problem:** Find kth missing positive number in sorted array.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class KthMissingPositive {
    public static int findKthPositive(int[] arr, int k) {
        int left = 0;
        int right = arr.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int missing = arr[mid] - (mid + 1);
            
            if (missing < k) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return left + k;
    }
    
    public static int findKthPositiveLinear(int[] arr, int k) {
        for (int num : arr) {
            if (num <= k) {
                k++;
            } else {
                break;
            }
        }
        return k;
    }
}
```

### 26. Aggressive Cows
**Problem:** Place cows in stalls such that minimum distance is maximized.  
**Time Complexity:** O(n log n + n log max_distance)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class AggressiveCows {
    public static int aggressiveCows(int[] stalls, int cows) {
        Arrays.sort(stalls);
        
        int left = 1;
        int right = stalls[stalls.length - 1] - stalls[0];
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (canPlaceCows(stalls, cows, mid)) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return right;
    }
    
    private static boolean canPlaceCows(int[] stalls, int cows, int minDistance) {
        int cowsPlaced = 1;
        int lastPosition = stalls[0];
        
        for (int i = 1; i < stalls.length; i++) {
            if (stalls[i] - lastPosition >= minDistance) {
                cowsPlaced++;
                lastPosition = stalls[i];
                if (cowsPlaced >= cows) {
                    return true;
                }
            }
        }
        
        return false;
    }
}
```

### 27. Book Allocation Problem
**Problem:** Allocate books to students such that maximum pages assigned is minimized.  
**Time Complexity:** O(n log sum)  
**Space Complexity:** O(1)

```java
public class BookAllocation {
    public static int allocateBooks(int[] books, int students) {
        if (students > books.length) return -1;
        
        int left = getMax(books);
        int right = getSum(books);
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (canAllocate(books, students, mid)) {
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    private static boolean canAllocate(int[] books, int students, int maxPages) {
        int studentsUsed = 1;
        int currentPages = 0;
        
        for (int pages : books) {
            if (currentPages + pages <= maxPages) {
                currentPages += pages;
            } else {
                studentsUsed++;
                currentPages = pages;
                if (studentsUsed > students) {
                    return false;
                }
            }
        }
        
        return true;
    }
    
    private static int getMax(int[] books) {
        int max = books[0];
        for (int book : books) {
            max = Math.max(max, book);
        }
        return max;
    }
    
    private static int getSum(int[] books) {
        int sum = 0;
        for (int book : books) {
            sum += book;
        }
        return sum;
    }
}
```

### 28. Split Array - Largest Sum
**Problem:** Split array into m subarrays such that largest sum is minimized.  
**Time Complexity:** O(n log sum)  
**Space Complexity:** O(1)

```java
public class SplitArrayLargestSum {
    public static int splitArray(int[] nums, int m) {
        int left = getMax(nums);
        int right = getSum(nums);
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            
            if (canSplit(nums, m, mid)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        
        return left;
    }
    
    private static boolean canSplit(int[] nums, int m, int maxSum) {
        int subarrays = 1;
        int currentSum = 0;
        
        for (int num : nums) {
            if (currentSum + num <= maxSum) {
                currentSum += num;
            } else {
                subarrays++;
                currentSum = num;
                if (subarrays > m) {
                    return false;
                }
            }
        }
        
        return true;
    }
    
    private static int getMax(int[] nums) {
        int max = nums[0];
        for (int num : nums) {
            max = Math.max(max, num);
        }
        return max;
    }
    
    private static int getSum(int[] nums) {
        int sum = 0;
        for (int num : nums) {
            sum += num;
        }
        return sum;
    }
}
```

### 29. Minimize Max Distance to Gas Station
**Problem:** Add k gas stations to minimize maximum distance between consecutive stations.  
**Time Complexity:** O(n log max_distance)  
**Space Complexity:** O(1)

```java
public class MinimizeMaxDistance {
    public static double minmaxGasDist(int[] stations, int k) {
        double left = 0;
        double right = 0;
        
        for (int i = 1; i < stations.length; i++) {
            right = Math.max(right, stations[i] - stations[i - 1]);
        }
        
        double eps = 1e-6;
        
        while (right - left > eps) {
            double mid = left + (right - left) / 2;
            
            if (canPlace(stations, k, mid)) {
                right = mid;
            } else {
                left = mid;
            }
        }
        
        return left;
    }
    
    private static boolean canPlace(int[] stations, int k, double maxDistance) {
        int gasStations = 0;
        
        for (int i = 1; i < stations.length; i++) {
            double distance = stations[i] - stations[i - 1];
            gasStations += (int) (distance / maxDistance);
        }
        
        return gasStations <= k;
    }
}
```

### 30. Median of Two Sorted Arrays
**Problem:** Find median of two sorted arrays.  
**Time Complexity:** O(log min(m, n))  
**Space Complexity:** O(1)

```java
public class MedianTwoSortedArrays {
    public static double findMedianSortedArrays(int[] nums1, int[] nums2) {
        if (nums1.length > nums2.length) {
            return findMedianSortedArrays(nums2, nums1);
        }
        
        int m = nums1.length;
        int n = nums2.length;
        
        int left = 0;
        int right = m;
        
        while (left <= right) {
            int cut1 = left + (right - left) / 2;
            int cut2 = (m + n + 1) / 2 - cut1;
            
            int left1 = cut1 == 0 ? Integer.MIN_VALUE : nums1[cut1 - 1];
            int left2 = cut2 == 0 ? Integer.MIN_VALUE : nums2[cut2 - 1];
            
            int right1 = cut1 == m ? Integer.MAX_VALUE : nums1[cut1];
            int right2 = cut2 == n ? Integer.MAX_VALUE : nums2[cut2];
            
            if (left1 <= right2 && left2 <= right1) {
                if ((m + n) % 2 == 1) {
                    return Math.max(left1, left2);
                } else {
                    return (Math.max(left1, left2) + Math.min(right1, right2)) / 2.0;
                }
            } else if (left1 > right2) {
                right = cut1 - 1;
            } else {
                left = cut1 + 1;
            }
        }
        
        return 1.0;
    }
}
```

### 31. Kth Element of Two Sorted Arrays
**Problem:** Find kth element in combined sorted arrays.  
**Time Complexity:** O(log min(m, n))  
**Space Complexity:** O(1)

```java
public class KthElementTwoSorted {
    public static int kthElement(int[] arr1, int[] arr2, int k) {
        if (arr1.length > arr2.length) {
            return kthElement(arr2, arr1, k);
        }
        
        int m = arr1.length;
        int n = arr2.length;
        
        int left = Math.max(0, k - n);
        int right = Math.min(k, m);
        
        while (left <= right) {
            int cut1 = left + (right - left) / 2;
            int cut2 = k - cut1;
            
            int left1 = cut1 == 0 ? Integer.MIN_VALUE : arr1[cut1 - 1];
            int left2 = cut2 == 0 ? Integer.MIN_VALUE : arr2[cut2 - 1];
            
            int right1 = cut1 == m ? Integer.MAX_VALUE : arr1[cut1];
            int right2 = cut2 == n ? Integer.MAX_VALUE : arr2[cut2];
            
            if (left1 <= right2 && left2 <= right1) {
                return Math.max(left1, left2);
            } else if (left1 > right2) {
                right = cut1 - 1;
            } else {
                left = cut1 + 1;
            }
        }
        
        return 1;
    }
}
```

---


## Strings

### 1. Remove Outermost Parentheses
**Problem:** Remove outermost parentheses from every primitive string.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class RemoveOuterParentheses {
    public static String removeOuterParentheses(String s) {
        StringBuilder result = new StringBuilder();
        int depth = 0;
        
        for (char c : s.toCharArray()) {
            if (c == '(') {
                if (depth > 0) {
                    result.append(c);
                }
                depth++;
            } else {
                depth--;
                if (depth > 0) {
                    result.append(c);
                }
            }
        }
        
        return result.toString();
    }
    
    public static String removeOuterParenthesesAlternative(String s) {
        StringBuilder result = new StringBuilder();
        int balance = 0;
        
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (c == '(' && balance++ > 0) {
                result.append(c);
            } else if (c == ')' && balance-- > 1) {
                result.append(c);
            }
        }
        
        return result.toString();
    }
}
```

### 2. Reverse Words in String / Check Palindrome
**Problem:** Reverse words in a string and check string palindrome.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class ReverseWords {
    public static String reverseWords(String s) {
        String[] words = s.trim().split("\\s+");
        StringBuilder result = new StringBuilder();
        
        for (int i = words.length - 1; i >= 0; i--) {
            result.append(words[i]);
            if (i > 0) {
                result.append(" ");
            }
        }
        
        return result.toString();
    }
    
    public static String reverseWordsOptimal(String s) {
        char[] chars = s.toCharArray();
        int n = chars.length;
        
        reverse(chars, 0, n - 1);
        reverseWords(chars, n);
        return cleanSpaces(chars, n);
    }
    
    private static void reverse(char[] chars, int start, int end) {
        while (start < end) {
            char temp = chars[start];
            chars[start] = chars[end];
            chars[end] = temp;
            start++;
            end--;
        }
    }
    
    private static void reverseWords(char[] chars, int n) {
        int start = 0, end = 0;
        
        while (start < n) {
            while (end < n && chars[end] != ' ') {
                end++;
            }
            reverse(chars, start, end - 1);
            start = end + 1;
            end++;
        }
    }
    
    private static String cleanSpaces(char[] chars, int n) {
        int slow = 0, fast = 0;
        
        while (fast < n) {
            while (fast < n && chars[fast] == ' ') {
                fast++;
            }
            while (fast < n && chars[fast] != ' ') {
                chars[slow++] = chars[fast++];
            }
            while (fast < n && chars[fast] == ' ') {
                fast++;
            }
            if (fast < n) {
                chars[slow++] = ' ';
            }
        }
        
        return new String(chars, 0, slow);
    }
    
    public static boolean isPalindrome(String s) {
        int left = 0;
        int right = s.length() - 1;
        
        while (left < right) {
            while (left < right && !Character.isAlphaNumeric(s.charAt(left))) {
                left++;
            }
            while (left < right && !Character.isAlphaNumeric(s.charAt(right))) {
                right--;
            }
            
            if (Character.toLowerCase(s.charAt(left)) != Character.toLowerCase(s.charAt(right))) {
                return false;
            }
            
            left++;
            right--;
        }
        
        return true;
    }
}
```

### 3. Largest Odd Number in String
**Problem:** Find largest odd number that can be formed from digits in string.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LargestOddNumber {
    public static String largestOddNumber(String num) {
        for (int i = num.length() - 1; i >= 0; i--) {
            if ((num.charAt(i) - '0') % 2 == 1) {
                return num.substring(0, i + 1);
            }
        }
        return "";
    }
    
    public static String largestOddNumberAlternative(String num) {
        int lastOddIndex = -1;
        
        for (int i = num.length() - 1; i >= 0; i--) {
            int digit = num.charAt(i) - '0';
            if (digit % 2 == 1) {
                lastOddIndex = i;
                break;
            }
        }
        
        return lastOddIndex == -1 ? "" : num.substring(0, lastOddIndex + 1);
    }
}
```

### 4. Longest Common Prefix
**Problem:** Find longest common prefix among array of strings.  
**Time Complexity:** O(S) where S is sum of all characters  
**Space Complexity:** O(1)

```java
public class LongestCommonPrefix {
    public static String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0) return "";
        
        String prefix = strs[0];
        
        for (int i = 1; i < strs.length; i++) {
            while (strs[i].indexOf(prefix) != 0) {
                prefix = prefix.substring(0, prefix.length() - 1);
                if (prefix.isEmpty()) return "";
            }
        }
        
        return prefix;
    }
    
    public static String longestCommonPrefixVertical(String[] strs) {
        if (strs == null || strs.length == 0) return "";
        
        for (int i = 0; i < strs[0].length(); i++) {
            char c = strs[0].charAt(i);
            for (int j = 1; j < strs.length; j++) {
                if (i >= strs[j].length() || strs[j].charAt(i) != c) {
                    return strs[0].substring(0, i);
                }
            }
        }
        
        return strs[0];
    }
    
    public static String longestCommonPrefixDivideConquer(String[] strs) {
        if (strs == null || strs.length == 0) return "";
        return longestCommonPrefix(strs, 0, strs.length - 1);
    }
    
    private static String longestCommonPrefix(String[] strs, int left, int right) {
        if (left == right) {
            return strs[left];
        } else {
            int mid = (left + right) / 2;
            String lcpLeft = longestCommonPrefix(strs, left, mid);
            String lcpRight = longestCommonPrefix(strs, mid + 1, right);
            return commonPrefix(lcpLeft, lcpRight);
        }
    }
    
    private static String commonPrefix(String left, String right) {
        int min = Math.min(left.length(), right.length());
        for (int i = 0; i < min; i++) {
            if (left.charAt(i) != right.charAt(i)) {
                return left.substring(0, i);
            }
        }
        return left.substring(0, min);
    }
}
```

### 5. Isomorphic Strings
**Problem:** Check if two strings are isomorphic.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1) - constant space for ASCII characters

```java
import java.util.*;

public class IsomorphicStrings {
    public static boolean isIsomorphic(String s, String t) {
        if (s.length() != t.length()) return false;
        
        Map<Character, Character> mapST = new HashMap<>();
        Map<Character, Character> mapTS = new HashMap<>();
        
        for (int i = 0; i < s.length(); i++) {
            char c1 = s.charAt(i);
            char c2 = t.charAt(i);
            
            if (mapST.containsKey(c1) && mapST.get(c1) != c2) {
                return false;
            }
            
            if (mapTS.containsKey(c2) && mapTS.get(c2) != c1) {
                return false;
            }
            
            mapST.put(c1, c2);
            mapTS.put(c2, c1);
        }
        
        return true;
    }
    
    public static boolean isIsomorphicArray(String s, String t) {
        if (s.length() != t.length()) return false;
        
        int[] mapS = new int[256];
        int[] mapT = new int[256];
        
        for (int i = 0; i < s.length(); i++) {
            if (mapS[s.charAt(i)] != mapT[t.charAt(i)]) {
                return false;
            }
            mapS[s.charAt(i)] = i + 1;
            mapT[t.charAt(i)] = i + 1;
        }
        
        return true;
    }
}
```

### 6. Check String Rotation
**Problem:** Check if one string is rotation of another.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class StringRotation {
    public static boolean isRotation(String s1, String s2) {
        if (s1.length() != s2.length()) return false;
        if (s1.length() == 0) return true;
        
        return (s1 + s1).contains(s2);
    }
    
    public static boolean isRotationKMP(String s1, String s2) {
        if (s1.length() != s2.length()) return false;
        if (s1.length() == 0) return true;
        
        String concatenated = s1 + s1;
        return kmpSearch(concatenated, s2) != -1;
    }
    
    private static int kmpSearch(String text, String pattern) {
        int[] lps = computeLPSArray(pattern);
        int i = 0, j = 0;
        
        while (i < text.length()) {
            if (text.charAt(i) == pattern.charAt(j)) {
                i++;
                j++;
            }
            
            if (j == pattern.length()) {
                return i - j;
            } else if (i < text.length() && text.charAt(i) != pattern.charAt(j)) {
                if (j != 0) {
                    j = lps[j - 1];
                } else {
                    i++;
                }
            }
        }
        
        return -1;
    }
    
    private static int[] computeLPSArray(String pattern) {
        int[] lps = new int[pattern.length()];
        int len = 0;
        int i = 1;
        
        while (i < pattern.length()) {
            if (pattern.charAt(i) == pattern.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            } else {
                if (len != 0) {
                    len = lps[len - 1];
                } else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        
        return lps;
    }
}
```

### 7. Valid Anagram
**Problem:** Check if two strings are anagrams of each other.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1) for lowercase letters

```java
public class ValidAnagram {
    public static boolean isAnagram(String s, String t) {
        if (s.length() != t.length()) return false;
        
        int[] count = new int[26];
        
        for (int i = 0; i < s.length(); i++) {
            count[s.charAt(i) - 'a']++;
            count[t.charAt(i) - 'a']--;
        }
        
        for (int c : count) {
            if (c != 0) return false;
        }
        
        return true;
    }
    
    public static boolean isAnagramSort(String s, String t) {
        if (s.length() != t.length()) return false;
        
        char[] sArray = s.toCharArray();
        char[] tArray = t.toCharArray();
        
        Arrays.sort(sArray);
        Arrays.sort(tArray);
        
        return Arrays.equals(sArray, tArray);
    }
    
    public static boolean isAnagramMap(String s, String t) {
        if (s.length() != t.length()) return false;
        
        Map<Character, Integer> charCount = new HashMap<>();
        
        for (char c : s.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) + 1);
        }
        
        for (char c : t.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) - 1);
            if (charCount.get(c) == 0) {
                charCount.remove(c);
            }
        }
        
        return charCount.isEmpty();
    }
}
```

### 8. Sort Characters by Frequency
**Problem:** Sort characters by frequency in descending order.  
**Time Complexity:** O(n log k) where k is number of unique characters  
**Space Complexity:** O(n)

```java
import java.util.*;

public class SortByFrequency {
    public static String frequencySort(String s) {
        Map<Character, Integer> freqMap = new HashMap<>();
        for (char c : s.toCharArray()) {
            freqMap.put(c, freqMap.getOrDefault(c, 0) + 1);
        }
        
        PriorityQueue<Character> pq = new PriorityQueue<>(
            (a, b) -> freqMap.get(b) - freqMap.get(a)
        );
        pq.addAll(freqMap.keySet());
        
        StringBuilder result = new StringBuilder();
        while (!pq.isEmpty()) {
            char c = pq.poll();
            int freq = freqMap.get(c);
            for (int i = 0; i < freq; i++) {
                result.append(c);
            }
        }
        
        return result.toString();
    }
    
    public static String frequencySortBucket(String s) {
        Map<Character, Integer> freqMap = new HashMap<>();
        for (char c : s.toCharArray()) {
            freqMap.put(c, freqMap.getOrDefault(c, 0) + 1);
        }
        
        List<Character>[] buckets = new List[s.length() + 1];
        for (char c : freqMap.keySet()) {
            int freq = freqMap.get(c);
            if (buckets[freq] == null) {
                buckets[freq] = new ArrayList<>();
            }
            buckets[freq].add(c);
        }
        
        StringBuilder result = new StringBuilder();
        for (int i = buckets.length - 1; i >= 0; i--) {
            if (buckets[i] != null) {
                for (char c : buckets[i]) {
                    for (int j = 0; j < i; j++) {
                        result.append(c);
                    }
                }
            }
        }
        
        return result.toString();
    }
}
```

### 9. Maximum Nesting Depth of Parentheses
**Problem:** Find maximum nesting depth of parentheses.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MaxNestingDepth {
    public static int maxDepth(String s) {
        int currentDepth = 0;
        int maxDepth = 0;
        
        for (char c : s.toCharArray()) {
            if (c == '(') {
                currentDepth++;
                maxDepth = Math.max(maxDepth, currentDepth);
            } else if (c == ')') {
                currentDepth--;
            }
        }
        
        return maxDepth;
    }
    
    public static int maxDepthStack(String s) {
        Stack<Character> stack = new Stack<>();
        int maxDepth = 0;
        
        for (char c : s.toCharArray()) {
            if (c == '(') {
                stack.push(c);
                maxDepth = Math.max(maxDepth, stack.size());
            } else if (c == ')') {
                if (!stack.isEmpty()) {
                    stack.pop();
                }
            }
        }
        
        return maxDepth;
    }
}
```

### 10. Roman to Integer and Vice Versa
**Problem:** Convert Roman numerals to integer and integer to Roman.  
**Time Complexity:** O(1) - bounded by constant factors  
**Space Complexity:** O(1)

```java
import java.util.*;

public class RomanInteger {
    public static int romanToInt(String s) {
        Map<Character, Integer> romanMap = new HashMap<>();
        romanMap.put('I', 1);
        romanMap.put('V', 5);
        romanMap.put('X', 10);
        romanMap.put('L', 50);
        romanMap.put('C', 100);
        romanMap.put('D', 500);
        romanMap.put('M', 1000);
        
        int result = 0;
        int prevValue = 0;
        
        for (int i = s.length() - 1; i >= 0; i--) {
            int currentValue = romanMap.get(s.charAt(i));
            
            if (currentValue < prevValue) {
                result -= currentValue;
            } else {
                result += currentValue;
            }
            
            prevValue = currentValue;
        }
        
        return result;
    }
    
    public static String intToRoman(int num) {
        int[] values = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        String[] symbols = {"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};
        
        StringBuilder result = new StringBuilder();
        
        for (int i = 0; i < values.length; i++) {
            int count = num / values[i];
            if (count > 0) {
                for (int j = 0; j < count; j++) {
                    result.append(symbols[i]);
                }
                num %= values[i];
            }
        }
        
        return result.toString();
    }
    
    public static int romanToIntOptimal(String s) {
        int result = 0;
        int prev = 0;
        
        for (int i = s.length() - 1; i >= 0; i--) {
            int current = getValue(s.charAt(i));
            
            if (current < prev) {
                result -= current;
            } else {
                result += current;
            }
            
            prev = current;
        }
        
        return result;
    }
    
    private static int getValue(char c) {
        switch (c) {
            case 'I': return 1;
            case 'V': return 5;
            case 'X': return 10;
            case 'L': return 50;
            case 'C': return 100;
            case 'D': return 500;
            case 'M': return 1000;
            default: return 0;
        }
    }
}
```

### 11. String to Integer (atoi)
**Problem:** Convert string to integer with proper handling of edge cases.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class StringToInteger {
    public static int myAtoi(String s) {
        if (s == null || s.length() == 0) return 0;
        
        int index = 0;
        int sign = 1;
        long result = 0;
        
        while (index < s.length() && s.charAt(index) == ' ') {
            index++;
        }
        
        if (index < s.length()) {
            if (s.charAt(index) == '+') {
                sign = 1;
                index++;
            } else if (s.charAt(index) == '-') {
                sign = -1;
                index++;
            }
        }
        
        while (index < s.length() && Character.isDigit(s.charAt(index))) {
            result = result * 10 + (s.charAt(index) - '0');
            
            if (sign == 1 && result > Integer.MAX_VALUE) {
                return Integer.MAX_VALUE;
            }
            if (sign == -1 && (-result) < Integer.MIN_VALUE) {
                return Integer.MIN_VALUE;
            }
            
            index++;
        }
        
        return (int) (sign * result);
    }
    
    public static int myAtoiFiniteStateMachine(String s) {
        final int INT_MAX = Integer.MAX_VALUE;
        final int INT_MIN = Integer.MIN_VALUE;
        
        int index = 0;
        int sign = 1;
        int result = 0;
        
        if (s.length() == 0) return 0;
        
        while (index < s.length() && s.charAt(index) == ' ') {
            index++;
        }
        
        if (index < s.length() && (s.charAt(index) == '+' || s.charAt(index) == '-')) {
            sign = s.charAt(index) == '+' ? 1 : -1;
            index++;
        }
        
        while (index < s.length() && Character.isDigit(s.charAt(index))) {
            int digit = s.charAt(index) - '0';
            
            if (result > INT_MAX / 10 || (result == INT_MAX / 10 && digit > INT_MAX % 10)) {
                return sign == 1 ? INT_MAX : INT_MIN;
            }
            
            result = result * 10 + digit;
            index++;
        }
        
        return sign * result;
    }
}
```

### 12. Count Number of Substrings
**Problem:** Count substrings with exactly K distinct characters.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1) - fixed alphabet size

```java
import java.util.*;

public class CountSubstrings {
    public static int countSubstringsWithKDistinct(String s, int k) {
        return atMostK(s, k) - atMostK(s, k - 1);
    }
    
    private static int atMostK(String s, int k) {
        if (k == 0) return 0;
        
        Map<Character, Integer> charCount = new HashMap<>();
        int left = 0;
        int result = 0;
        
        for (int right = 0; right < s.length(); right++) {
            char rightChar = s.charAt(right);
            charCount.put(rightChar, charCount.getOrDefault(rightChar, 0) + 1);
            
            while (charCount.size() > k) {
                char leftChar = s.charAt(left);
                charCount.put(leftChar, charCount.get(leftChar) - 1);
                if (charCount.get(leftChar) == 0) {
                    charCount.remove(leftChar);
                }
                left++;
            }
            
            result += right - left + 1;
        }
        
        return result;
    }
    
    public static int countSubstringsWithAllThreeChars(String s) {
        int[] lastIndex = {-1, -1, -1};
        int result = 0;
        
        for (int i = 0; i < s.length(); i++) {
            lastIndex[s.charAt(i) - 'a'] = i;
            result += 1 + Math.min(lastIndex[0], Math.min(lastIndex[1], lastIndex[2]));
        }
        
        return result;
    }
}
```

### 13. Longest Palindromic Substring
**Problem:** Find longest palindromic substring.  
**Time Complexity:** O(n²)  
**Space Complexity:** O(1)

```java
public class LongestPalindromicSubstring {
    public static String longestPalindrome(String s) {
        if (s == null || s.length() < 2) return s;
        
        int start = 0;
        int maxLength = 1;
        
        for (int i = 0; i < s.length(); i++) {
            int len1 = expandAroundCenter(s, i, i);
            int len2 = expandAroundCenter(s, i, i + 1);
            int len = Math.max(len1, len2);
            
            if (len > maxLength) {
                maxLength = len;
                start = i - (len - 1) / 2;
            }
        }
        
        return s.substring(start, start + maxLength);
    }
    
    private static int expandAroundCenter(String s, int left, int right) {
        while (left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) {
            left--;
            right++;
        }
        return right - left - 1;
    }
    
    public static String longestPalindromeDP(String s) {
        int n = s.length();
        if (n <= 1) return s;
        
        boolean[][] dp = new boolean[n][n];
        String result = "";
        
        for (int len = 1; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                
                if (len == 1) {
                    dp[i][j] = true;
                } else if (len == 2) {
                    dp[i][j] = (s.charAt(i) == s.charAt(j));
                } else {
                    dp[i][j] = (s.charAt(i) == s.charAt(j) && dp[i + 1][j - 1]);
                }
                
                if (dp[i][j] && len > result.length()) {
                    result = s.substring(i, j + 1);
                }
            }
        }
        
        return result;
    }
    
    public static String longestPalindromeManacher(String s) {
        if (s == null || s.length() == 0) return "";
        
        String processed = preprocess(s);
        int[] P = new int[processed.length()];
        int center = 0, right = 0;
        
        for (int i = 1; i < processed.length() - 1; i++) {
            int mirror = 2 * center - i;
            
            if (i < right) {
                P[i] = Math.min(right - i, P[mirror]);
            }
            
            try {
                while (processed.charAt(i + (1 + P[i])) == processed.charAt(i - (1 + P[i]))) {
                    P[i]++;
                }
            } catch (StringIndexOutOfBoundsException e) {
            }
            
            if (i + P[i] > right) {
                center = i;
                right = i + P[i];
            }
        }
        
        int maxLength = 0;
        int centerIndex = 0;
        for (int i = 1; i < processed.length() - 1; i++) {
            if (P[i] > maxLength) {
                maxLength = P[i];
                centerIndex = i;
            }
        }
        
        int start = (centerIndex - maxLength) / 2;
        return s.substring(start, start + maxLength);
    }
    
    private static String preprocess(String s) {
        StringBuilder sb = new StringBuilder("^");
        for (char c : s.toCharArray()) {
            sb.append("#").append(c);
        }
        sb.append("#$");
        return sb.toString();
    }
}
```

### 14. Sum of Beauty of All Substrings
**Problem:** Calculate sum of beauty of all substrings (max_freq - min_freq).  
**Time Complexity:** O(n²)  
**Space Complexity:** O(1) - fixed alphabet size

```java
import java.util.*;

public class SumOfBeauty {
    public static int beautySum(String s) {
        int totalBeauty = 0;
        
        for (int i = 0; i < s.length(); i++) {
            Map<Character, Integer> freqMap = new HashMap<>();
            
            for (int j = i; j < s.length(); j++) {
                char c = s.charAt(j);
                freqMap.put(c, freqMap.getOrDefault(c, 0) + 1);
                
                totalBeauty += getBeauty(freqMap);
            }
        }
        
        return totalBeauty;
    }
    
    private static int getBeauty(Map<Character, Integer> freqMap) {
        if (freqMap.size() <= 1) return 0;
        
        int maxFreq = 0;
        int minFreq = Integer.MAX_VALUE;
        
        for (int freq : freqMap.values()) {
            maxFreq = Math.max(maxFreq, freq);
            minFreq = Math.min(minFreq, freq);
        }
        
        return maxFreq - minFreq;
    }
    
    public static int beautySumOptimal(String s) {
        int totalBeauty = 0;
        
        for (int i = 0; i < s.length(); i++) {
            int[] freq = new int[26];
            
            for (int j = i; j < s.length(); j++) {
                freq[s.charAt(j) - 'a']++;
                
                int maxFreq = 0;
                int minFreq = Integer.MAX_VALUE;
                
                for (int f : freq) {
                    if (f > 0) {
                        maxFreq = Math.max(maxFreq, f);
                        minFreq = Math.min(minFreq, f);
                    }
                }
                
                totalBeauty += maxFreq - minFreq;
            }
        }
        
        return totalBeauty;
    }
}
```

### 15. Reverse Every Word in String
**Problem:** Reverse each word in string while maintaining word positions.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class ReverseEveryWord {
    public static String reverseWords(String s) {
        String[] words = s.split(" ");
        StringBuilder result = new StringBuilder();
        
        for (int i = 0; i < words.length; i++) {
            result.append(reverseString(words[i]));
            if (i < words.length - 1) {
                result.append(" ");
            }
        }
        
        return result.toString();
    }
    
    private static String reverseString(String str) {
        char[] chars = str.toCharArray();
        int left = 0;
        int right = chars.length - 1;
        
        while (left < right) {
            char temp = chars[left];
            chars[left] = chars[right];
            chars[right] = temp;
            left++;
            right--;
        }
        
        return new String(chars);
    }
    
    public static String reverseWordsInPlace(String s) {
        char[] chars = s.toCharArray();
        int start = 0;
        
        for (int end = 0; end <= chars.length; end++) {
            if (end == chars.length || chars[end] == ' ') {
                reverseRange(chars, start, end - 1);
                start = end + 1;
            }
        }
        
        return new String(chars);
    }
    
    private static void reverseRange(char[] chars, int start, int end) {
        while (start < end) {
            char temp = chars[start];
            chars[start] = chars[end];
            chars[end] = temp;
            start++;
            end--;
        }
    }
    
    public static String reverseWordsOptimal(String s) {
        StringBuilder result = new StringBuilder();
        int i = 0;
        
        while (i < s.length()) {
            if (s.charAt(i) == ' ') {
                result.append(' ');
                i++;
            } else {
                StringBuilder word = new StringBuilder();
                while (i < s.length() && s.charAt(i) != ' ') {
                    word.append(s.charAt(i));
                    i++;
                }
                result.append(word.reverse());
            }
        }
        
        return result.toString();
    }
}
```

### 16. Minimum Number of Bracket Reversals
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class MinimumBracketReversals {
    public static int minReversals(String s) {
        int n = s.length();
        if (n % 2 != 0) return -1;
        
        Stack<Character> stack = new Stack<>();
        
        for (char c : s.toCharArray()) {
            if (c == '{') {
                stack.push(c);
            } else {
                if (!stack.isEmpty() && stack.peek() == '{') {
                    stack.pop();
                } else {
                    stack.push(c);
                }
            }
        }
        
        int close = 0, open = 0;
        while (!stack.isEmpty()) {
            if (stack.pop() == '{') {
                open++;
            } else {
                close++;
            }
        }
        
        return (close + 1) / 2 + (open + 1) / 2;
    }
    
    public static int minReversalsOptimized(String s) {
        int n = s.length();
        if (n % 2 != 0) return -1;
        
        int open = 0, close = 0;
        
        for (char c : s.toCharArray()) {
            if (c == '{') {
                open++;
            } else {
                if (open > 0) {
                    open--;
                } else {
                    close++;
                }
            }
        }
        
        return (close + 1) / 2 + (open + 1) / 2;
    }
}
```

### 17. Count and Say
**Time:** O(4^n/3) **Space:** O(4^n/3)

```java
public class CountAndSay {
    public static String countAndSay(int n) {
        String result = "1";
        
        for (int i = 2; i <= n; i++) {
            result = getNext(result);
        }
        
        return result;
    }
    
    private static String getNext(String s) {
        StringBuilder sb = new StringBuilder();
        int count = 1;
        char current = s.charAt(0);
        
        for (int i = 1; i < s.length(); i++) {
            if (s.charAt(i) == current) {
                count++;
            } else {
                sb.append(count).append(current);
                current = s.charAt(i);
                count = 1;
            }
        }
        
        sb.append(count).append(current);
        return sb.toString();
    }
    
    public static String countAndSayRecursive(int n) {
        if (n == 1) return "1";
        
        String prev = countAndSayRecursive(n - 1);
        StringBuilder sb = new StringBuilder();
        
        int count = 1;
        char current = prev.charAt(0);
        
        for (int i = 1; i < prev.length(); i++) {
            if (prev.charAt(i) == current) {
                count++;
            } else {
                sb.append(count).append(current);
                current = prev.charAt(i);
                count = 1;
            }
        }
        
        sb.append(count).append(current);
        return sb.toString();
    }
}
```

---

### 18. Rolling Hash Implementation
**Time:** O(n + q) **Space:** O(n)

```java
public class StringHashing {
    private static final long MOD = 1000000007;
    private static final long BASE = 31;
    
    private long[] hash;
    private long[] pow;
    private int n;
    
    public StringHashing(String s) {
        n = s.length();
        hash = new long[n + 1];
        pow = new long[n + 1];
        
        pow[0] = 1;
        for (int i = 0; i < n; i++) {
            pow[i + 1] = (pow[i] * BASE) % MOD;
        }
        
        for (int i = 0; i < n; i++) {
            hash[i + 1] = (hash[i] * BASE + s.charAt(i)) % MOD;
        }
    }
    
    public long getHash(int l, int r) {
        long result = hash[r + 1] - (hash[l] * pow[r - l + 1]) % MOD;
        return (result % MOD + MOD) % MOD;
    }
    
    public static boolean areEqual(String s1, int l1, int r1, String s2, int l2, int r2) {
        if (r1 - l1 != r2 - l2) return false;
        
        StringHashing h1 = new StringHashing(s1);
        StringHashing h2 = new StringHashing(s2);
        
        return h1.getHash(l1, r1) == h2.getHash(l2, r2);
    }
}
```

---

### 19. Rabin Karp Algorithm
**Time:** O(n + m) average, O(nm) worst **Space:** O(1)

```java
import java.util.*;

public class RabinKarp {
    private static final int PRIME = 101;
    
    public static List<Integer> search(String text, String pattern) {
        List<Integer> result = new ArrayList<>();
        int n = text.length();
        int m = pattern.length();
        
        if (m > n) return result;
        
        int patternHash = 0;
        int textHash = 0;
        int h = 1;
        
        for (int i = 0; i < m - 1; i++) {
            h = (h * 256) % PRIME;
        }
        
        for (int i = 0; i < m; i++) {
            patternHash = (256 * patternHash + pattern.charAt(i)) % PRIME;
            textHash = (256 * textHash + text.charAt(i)) % PRIME;
        }
        
        for (int i = 0; i <= n - m; i++) {
            if (patternHash == textHash) {
                boolean match = true;
                for (int j = 0; j < m; j++) {
                    if (text.charAt(i + j) != pattern.charAt(j)) {
                        match = false;
                        break;
                    }
                }
                if (match) result.add(i);
            }
            
            if (i < n - m) {
                textHash = (256 * (textHash - text.charAt(i) * h) + text.charAt(i + m)) % PRIME;
                if (textHash < 0) {
                    textHash = textHash + PRIME;
                }
            }
        }
        
        return result;
    }
    
    public static int searchFirst(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();
        
        if (m > n) return -1;
        
        int patternHash = 0;
        int textHash = 0;
        int h = 1;
        
        for (int i = 0; i < m - 1; i++) {
            h = (h * 256) % PRIME;
        }
        
        for (int i = 0; i < m; i++) {
            patternHash = (256 * patternHash + pattern.charAt(i)) % PRIME;
            textHash = (256 * textHash + text.charAt(i)) % PRIME;
        }
        
        for (int i = 0; i <= n - m; i++) {
            if (patternHash == textHash) {
                boolean match = true;
                for (int j = 0; j < m; j++) {
                    if (text.charAt(i + j) != pattern.charAt(j)) {
                        match = false;
                        break;
                    }
                }
                if (match) return i;
            }
            
            if (i < n - m) {
                textHash = (256 * (textHash - text.charAt(i) * h) + text.charAt(i + m)) % PRIME;
                if (textHash < 0) {
                    textHash = textHash + PRIME;
                }
            }
        }
        
        return -1;
    }
}
```

### 20. Z-Function
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class ZFunction {
    public static int[] zFunction(String s) {
        int n = s.length();
        int[] z = new int[n];
        int l = 0, r = 0;
        
        for (int i = 1; i < n; i++) {
            if (i <= r) {
                z[i] = Math.min(r - i + 1, z[i - l]);
            }
            
            while (i + z[i] < n && s.charAt(z[i]) == s.charAt(i + z[i])) {
                z[i]++;
            }
            
            if (i + z[i] - 1 > r) {
                l = i;
                r = i + z[i] - 1;
            }
        }
        
        return z;
    }
    
    public static List<Integer> searchPattern(String text, String pattern) {
        String combined = pattern + "$" + text;
        int[] z = zFunction(combined);
        
        List<Integer> result = new ArrayList<>();
        int patternLength = pattern.length();
        
        for (int i = patternLength + 1; i < combined.length(); i++) {
            if (z[i] == patternLength) {
                result.add(i - patternLength - 1);
            }
        }
        
        return result;
    }
    
    public static int searchFirst(String text, String pattern) {
        String combined = pattern + "$" + text;
        int[] z = zFunction(combined);
        
        int patternLength = pattern.length();
        
        for (int i = patternLength + 1; i < combined.length(); i++) {
            if (z[i] == patternLength) {
                return i - patternLength - 1;
            }
        }
        
        return -1;
    }
}
```

### 21. KMP Algorithm / LPS Array
**Time:** O(n + m) **Space:** O(m)

```java
import java.util.*;

public class KMPAlgorithm {
    public static int[] computeLPS(String pattern) {
        int m = pattern.length();
        int[] lps = new int[m];
        int len = 0;
        int i = 1;
        
        while (i < m) {
            if (pattern.charAt(i) == pattern.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            } else {
                if (len != 0) {
                    len = lps[len - 1];
                } else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        
        return lps;
    }
    
    public static List<Integer> searchPattern(String text, String pattern) {
        List<Integer> result = new ArrayList<>();
        int n = text.length();
        int m = pattern.length();
        
        int[] lps = computeLPS(pattern);
        
        int i = 0;
        int j = 0;
        
        while (i < n) {
            if (pattern.charAt(j) == text.charAt(i)) {
                j++;
                i++;
            }
            
            if (j == m) {
                result.add(i - j);
                j = lps[j - 1];
            } else if (i < n && pattern.charAt(j) != text.charAt(i)) {
                if (j != 0) {
                    j = lps[j - 1];
                } else {
                    i++;
                }
            }
        }
        
        return result;
    }
    
    public static int searchFirst(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();
        
        int[] lps = computeLPS(pattern);
        
        int i = 0;
        int j = 0;
        
        while (i < n) {
            if (pattern.charAt(j) == text.charAt(i)) {
                j++;
                i++;
            }
            
            if (j == m) {
                return i - j;
            } else if (i < n && pattern.charAt(j) != text.charAt(i)) {
                if (j != 0) {
                    j = lps[j - 1];
                } else {
                    i++;
                }
            }
        }
        
        return -1;
    }
}
```


### 22. Shortest Palindrome
**Time:** O(n) **Space:** O(n)

```java
public class ShortestPalindrome {
    public static String shortestPalindrome(String s) {
        if (s == null || s.length() <= 1) return s;
        
        String rev = new StringBuilder(s).reverse().toString();
        String combined = s + "#" + rev;
        
        int[] lps = computeLPS(combined);
        int palindromeLength = lps[combined.length() - 1];
        
        String prefix = rev.substring(0, s.length() - palindromeLength);
        return prefix + s;
    }
    
    private static int[] computeLPS(String pattern) {
        int m = pattern.length();
        int[] lps = new int[m];
        int len = 0;
        int i = 1;
        
        while (i < m) {
            if (pattern.charAt(i) == pattern.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            } else {
                if (len != 0) {
                    len = lps[len - 1];
                } else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        
        return lps;
    }
    
    public static String shortestPalindromeRollingHash(String s) {
        if (s == null || s.length() <= 1) return s;
        
        long base = 29;
        long mod = 1000000007;
        long hash1 = 0, hash2 = 0, pow = 1;
        int palindromeEnd = 0;
        
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            hash1 = (hash1 * base + (c - 'a' + 1)) % mod;
            hash2 = ((c - 'a' + 1) * pow + hash2) % mod;
            pow = (pow * base) % mod;
            
            if (hash1 == hash2) {
                palindromeEnd = i;
            }
        }
        
        String suffix = s.substring(palindromeEnd + 1);
        String prefix = new StringBuilder(suffix).reverse().toString();
        
        return prefix + s;
    }
}
```

### 23. Longest Happy Prefix
**Time:** O(n) **Space:** O(n)

```java
public class LongestHappyPrefix {
    public static String longestPrefix(String s) {
        int[] lps = computeLPS(s);
        int len = lps[s.length() - 1];
        return s.substring(0, len);
    }
    
    private static int[] computeLPS(String pattern) {
        int m = pattern.length();
        int[] lps = new int[m];
        int len = 0;
        int i = 1;
        
        while (i < m) {
            if (pattern.charAt(i) == pattern.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            } else {
                if (len != 0) {
                    len = lps[len - 1];
                } else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        
        return lps;
    }
    
    public static String longestPrefixRollingHash(String s) {
        long base = 31;
        long mod = 1000000007;
        
        long prefixHash = 0;
        long suffixHash = 0;
        long pow = 1;
        int maxLen = 0;
        
        for (int i = 0; i < s.length() - 1; i++) {
            prefixHash = (prefixHash * base + (s.charAt(i) - 'a' + 1)) % mod;
            
            suffixHash = ((s.charAt(s.length() - 1 - i) - 'a' + 1) * pow + suffixHash) % mod;
            pow = (pow * base) % mod;
            
            if (prefixHash == suffixHash) {
                maxLen = i + 1;
            }
        }
        
        return s.substring(0, maxLen);
    }
    
    public static int longestPrefixLength(String s) {
        int[] lps = computeLPS(s);
        return lps[s.length() - 1];
    }
}
```

### 24. Count Palindromic Subsequences
**Time:** O(n²) **Space:** O(n²)

```java
public class CountPalindromicSubsequences {
    public static int countPalindromicSubsequences(String s) {
        int n = s.length();
        int[][] dp = new int[n][n];
        
        for (int i = 0; i < n; i++) {
            dp[i][i] = 1;
        }
        
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                
                if (s.charAt(i) == s.charAt(j)) {
                    dp[i][j] = dp[i + 1][j] + dp[i][j - 1] + 1;
                } else {
                    dp[i][j] = dp[i + 1][j] + dp[i][j - 1] - dp[i + 1][j - 1];
                }
            }
        }
        
        return dp[0][n - 1];
    }
    
    public static int countPalindromicSubsequencesOptimized(String s) {
        int n = s.length();
        int[] prev = new int[n];
        int[] curr = new int[n];
        
        for (int i = 0; i < n; i++) {
            prev[i] = 1;
        }
        
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                
                if (s.charAt(i) == s.charAt(j)) {
                    if (len == 2) {
                        curr[i] = 3;
                    } else {
                        curr[i] = prev[i + 1] + prev[i] + 1;
                    }
                } else {
                    curr[i] = prev[i + 1] + prev[i];
                    if (len > 2) {
                        curr[i] -= prev[i + 1];
                    }
                }
            }
            
            int[] temp = prev;
            prev = curr;
            curr = temp;
        }
        
        return prev[0];
    }
    
    public static long countPalindromicSubsequencesMod(String s) {
        int MOD = 1000000007;
        int n = s.length();
        long[][] dp = new long[n][n];
        
        for (int i = 0; i < n; i++) {
            dp[i][i] = 1;
        }
        
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                
                if (s.charAt(i) == s.charAt(j)) {
                    dp[i][j] = (dp[i + 1][j] + dp[i][j - 1] + 1) % MOD;
                } else {
                    dp[i][j] = (dp[i + 1][j] + dp[i][j - 1] - dp[i + 1][j - 1] + MOD) % MOD;
                }
            }
        }
        
        return dp[0][n - 1];
    }
}
```


### String Comparison Utilities
```java
public class StringUtils {
    public static boolean isPalindrome(String s) {
        int left = 0, right = s.length() - 1;
        
        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        
        return true;
    }
    
    public static String reverse(String s) {
        return new StringBuilder(s).reverse().toString();
    }
    
    public static long polynomialHash(String s, long base, long mod) {
        long hash = 0;
        long pow = 1;
        
        for (char c : s.toCharArray()) {
            hash = (hash + (c - 'a' + 1) * pow) % mod;
            pow = (pow * base) % mod;
        }
        
        return hash;
    }
    
    public static boolean areAnagrams(String s1, String s2) {
        if (s1.length() != s2.length()) return false;
        
        int[] count = new int[26];
        
        for (int i = 0; i < s1.length(); i++) {
            count[s1.charAt(i) - 'a']++;
            count[s2.charAt(i) - 'a']--;
        }
        
        for (int c : count) {
            if (c != 0) return false;
        }
        
        return true;
    }
}
```

---

## LinkedList

```java
class ListNode {
    int val;
    ListNode next;
    
    ListNode() {}
    ListNode(int val) { this.val = val; }
    ListNode(int val, ListNode next) { this.val = val; this.next = next; }
}

class DoublyListNode {
    int val;
    DoublyListNode prev;
    DoublyListNode next;
    
    DoublyListNode() {}
    DoublyListNode(int val) { this.val = val; }
    DoublyListNode(int val, DoublyListNode prev, DoublyListNode next) {
        this.val = val;
        this.prev = prev;
        this.next = next;
    }
}
```

### 1. Introduction to LinkedList Structure
**Concept:** Understanding LinkedList node representation and basic structure.  


```java
public class LinkedListIntro {
    public static ListNode createNode(int val) {
        return new ListNode(val);
    }
    
    public static void printList(ListNode head) {
        ListNode current = head;
        while (current != null) {
            System.out.print(current.val + " -> ");
            current = current.next;
        }
        System.out.println("null");
    }
    
    public static ListNode createLinkedList(int[] arr) {
        if (arr.length == 0) return null;
        
        ListNode head = new ListNode(arr[0]);
        ListNode current = head;
        
        for (int i = 1; i < arr.length; i++) {
            current.next = new ListNode(arr[i]);
            current = current.next;
        }
        
        return head;
    }
}
```

### 2. Insert Node in LinkedList
**Problem:** Insert node at beginning, end, or specific position.  
**Time Complexity:** O(1) for beginning, O(n) for position/end  
**Space Complexity:** O(1)

```java
public class InsertNode {
    public static ListNode insertAtBeginning(ListNode head, int val) {
        ListNode newNode = new ListNode(val);
        newNode.next = head;
        return newNode;
    }
    
    public static ListNode insertAtEnd(ListNode head, int val) {
        ListNode newNode = new ListNode(val);
        
        if (head == null) return newNode;
        
        ListNode current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = newNode;
        
        return head;
    }
    
    public static ListNode insertAtPosition(ListNode head, int val, int position) {
        if (position == 0) {
            return insertAtBeginning(head, val);
        }
        
        ListNode newNode = new ListNode(val);
        ListNode current = head;
        
        for (int i = 0; i < position - 1 && current != null; i++) {
            current = current.next;
        }
        
        if (current != null) {
            newNode.next = current.next;
            current.next = newNode;
        }
        
        return head;
    }
    
    public static ListNode insertSorted(ListNode head, int val) {
        ListNode newNode = new ListNode(val);
        
        if (head == null || head.val >= val) {
            newNode.next = head;
            return newNode;
        }
        
        ListNode current = head;
        while (current.next != null && current.next.val < val) {
            current = current.next;
        }
        
        newNode.next = current.next;
        current.next = newNode;
        
        return head;
    }
}
```

### 3. Delete Node in LinkedList
**Problem:** Delete node by value, position, or reference.  
**Time Complexity:** O(n) for search, O(1) for deletion  
**Space Complexity:** O(1)

```java
public class DeleteNode {
    public static ListNode deleteByValue(ListNode head, int val) {
        if (head == null) return null;
        
        if (head.val == val) {
            return head.next;
        }
        
        ListNode current = head;
        while (current.next != null && current.next.val != val) {
            current = current.next;
        }
        
        if (current.next != null) {
            current.next = current.next.next;
        }
        
        return head;
    }
    
    public static ListNode deleteAtPosition(ListNode head, int position) {
        if (head == null) return null;
        
        if (position == 0) {
            return head.next;
        }
        
        ListNode current = head;
        for (int i = 0; i < position - 1 && current.next != null; i++) {
            current = current.next;
        }
        
        if (current.next != null) {
            current.next = current.next.next;
        }
        
        return head;
    }
    
    public static void deleteNodeWithReference(ListNode node) {
        if (node == null || node.next == null) return;
        
        node.val = node.next.val;
        node.next = node.next.next;
    }
    
    public static ListNode deleteAllOccurrences(ListNode head, int val) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode current = dummy;
        
        while (current.next != null) {
            if (current.next.val == val) {
                current.next = current.next.next;
            } else {
                current = current.next;
            }
        }
        
        return dummy.next;
    }
}
```

### 4. Find Length of LinkedList
**Problem:** Calculate total number of nodes in LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LinkedListLength {
    public static int getLength(ListNode head) {
        int length = 0;
        ListNode current = head;
        
        while (current != null) {
            length++;
            current = current.next;
        }
        
        return length;
    }
    
    public static int getLengthRecursive(ListNode head) {
        if (head == null) return 0;
        return 1 + getLengthRecursive(head.next);
    }
    
    public static boolean isEmpty(ListNode head) {
        return head == null;
    }
    
    public static int getLengthWithLoop(ListNode head) {
        if (hasLoop(head)) return -1;
        
        int length = 0;
        ListNode current = head;
        
        while (current != null) {
            length++;
            current = current.next;
        }
        
        return length;
    }
    
    private static boolean hasLoop(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        
        return false;
    }
}
```

### 5. Search Element in LinkedList
**Problem:** Find if element exists in LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class SearchElement {
    public static boolean search(ListNode head, int target) {
        ListNode current = head;
        
        while (current != null) {
            if (current.val == target) {
                return true;
            }
            current = current.next;
        }
        
        return false;
    }
    
    public static int searchIndex(ListNode head, int target) {
        ListNode current = head;
        int index = 0;
        
        while (current != null) {
            if (current.val == target) {
                return index;
            }
            current = current.next;
            index++;
        }
        
        return -1;
    }
    
    public static boolean searchRecursive(ListNode head, int target) {
        if (head == null) return false;
        if (head.val == target) return true;
        return searchRecursive(head.next, target);
    }
    
    public static ListNode searchNode(ListNode head, int target) {
        ListNode current = head;
        
        while (current != null) {
            if (current.val == target) {
                return current;
            }
            current = current.next;
        }
        
        return null;
    }
}
```

### 6. Introduction to Doubly LinkedList
**Concept:** Understanding DLL structure with prev and next pointers.  
**Time Complexity:** O(1) for basic operations  
**Space Complexity:** O(1)

```java
public class DoublyLinkedListIntro {
    public static DoublyListNode createNode(int val) {
        return new DoublyListNode(val);
    }
    
    public static void printForward(DoublyListNode head) {
        DoublyListNode current = head;
        System.out.print("Forward: ");
        while (current != null) {
            System.out.print(current.val + " <-> ");
            current = current.next;
        }
        System.out.println("null");
    }
    
    public static void printBackward(DoublyListNode tail) {
        DoublyListNode current = tail;
        System.out.print("Backward: ");
        while (current != null) {
            System.out.print(current.val + " <-> ");
            current = current.prev;
        }
        System.out.println("null");
    }
    
    public static DoublyListNode getTail(DoublyListNode head) {
        if (head == null) return null;
        
        while (head.next != null) {
            head = head.next;
        }
        
        return head;
    }
}
```

### 7. Insert Node in Doubly LinkedList
**Problem:** Insert node in DLL at various positions.  
**Time Complexity:** O(1) for beginning/end with tail, O(n) for position  
**Space Complexity:** O(1)

```java
public class InsertDLL {
    public static DoublyListNode insertAtBeginning(DoublyListNode head, int val) {
        DoublyListNode newNode = new DoublyListNode(val);
        
        if (head == null) return newNode;
        
        newNode.next = head;
        head.prev = newNode;
        
        return newNode;
    }
    
    public static DoublyListNode insertAtEnd(DoublyListNode head, int val) {
        DoublyListNode newNode = new DoublyListNode(val);
        
        if (head == null) return newNode;
        
        DoublyListNode tail = getTail(head);
        tail.next = newNode;
        newNode.prev = tail;
        
        return head;
    }
    
    public static DoublyListNode insertAtPosition(DoublyListNode head, int val, int position) {
        if (position == 0) {
            return insertAtBeginning(head, val);
        }
        
        DoublyListNode newNode = new DoublyListNode(val);
        DoublyListNode current = head;
        
        for (int i = 0; i < position && current != null; i++) {
            current = current.next;
        }
        
        if (current == null) {
            return insertAtEnd(head, val);
        }
        
        newNode.next = current;
        newNode.prev = current.prev;
        
        if (current.prev != null) {
            current.prev.next = newNode;
        } else {
            head = newNode;
        }
        
        current.prev = newNode;
        
        return head;
    }
    
    public static DoublyListNode insertAfterNode(DoublyListNode head, DoublyListNode node, int val) {
        if (node == null) return head;
        
        DoublyListNode newNode = new DoublyListNode(val);
        
        newNode.next = node.next;
        newNode.prev = node;
        
        if (node.next != null) {
            node.next.prev = newNode;
        }
        
        node.next = newNode;
        
        return head;
    }
    
    private static DoublyListNode getTail(DoublyListNode head) {
        while (head.next != null) {
            head = head.next;
        }
        return head;
    }
}
```

### 8. Delete Node in Doubly LinkedList
**Problem:** Delete node from DLL efficiently.  
**Time Complexity:** O(1) with node reference, O(n) for search  
**Space Complexity:** O(1)

```java
public class DeleteDLL {
    public static DoublyListNode deleteNode(DoublyListNode head, DoublyListNode node) {
        if (head == null || node == null) return head;
        
        if (head == node) {
            head = node.next;
        }
        
        if (node.next != null) {
            node.next.prev = node.prev;
        }
        
        if (node.prev != null) {
            node.prev.next = node.next;
        }
        
        return head;
    }
    
    public static DoublyListNode deleteByValue(DoublyListNode head, int val) {
        DoublyListNode current = head;
        
        while (current != null && current.val != val) {
            current = current.next;
        }
        
        if (current != null) {
            return deleteNode(head, current);
        }
        
        return head;
    }
    
    public static DoublyListNode deleteAtPosition(DoublyListNode head, int position) {
        if (head == null) return null;
        
        DoublyListNode current = head;
        
        for (int i = 0; i < position && current != null; i++) {
            current = current.next;
        }
        
        return deleteNode(head, current);
    }
    
    public static DoublyListNode deleteHead(DoublyListNode head) {
        if (head == null) return null;
        
        if (head.next != null) {
            head.next.prev = null;
        }
        
        return head.next;
    }
    
    public static DoublyListNode deleteTail(DoublyListNode head) {
        if (head == null) return null;
        if (head.next == null) return null;
        
        DoublyListNode tail = getTail(head);
        tail.prev.next = null;
        
        return head;
    }
    
    private static DoublyListNode getTail(DoublyListNode head) {
        while (head.next != null) {
            head = head.next;
        }
        return head;
    }
}
```

### 9. Reverse Doubly LinkedList
**Problem:** Reverse the direction of DLL.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class ReverseDLL {
    public static DoublyListNode reverse(DoublyListNode head) {
        if (head == null) return null;
        
        DoublyListNode current = head;
        DoublyListNode temp = null;
        
        while (current != null) {
            temp = current.prev;
            current.prev = current.next;
            current.next = temp;
            current = current.prev;
        }
        
        if (temp != null) {
            head = temp.prev;
        }
        
        return head;
    }
    
    public static DoublyListNode reverseRecursive(DoublyListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        DoublyListNode temp = head.prev;
        head.prev = head.next;
        head.next = temp;
        
        DoublyListNode newHead = reverseRecursive(head.prev);
        
        return newHead;
    }
    
    public static DoublyListNode reverseIterative(DoublyListNode head) {
        DoublyListNode current = head;
        DoublyListNode prev = null;
        
        while (current != null) {
            DoublyListNode next = current.next;
            
            current.next = prev;
            current.prev = next;
            
            prev = current;
            current = next;
        }
        
        return prev;
    }
}
```

### 10. Middle of LinkedList (Tortoise-Hare Method)
**Problem:** Find middle node efficiently.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class MiddleOfLinkedList {
    public static ListNode findMiddle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        
        return slow;
    }
    
    public static ListNode findMiddleForEvenLength(ListNode head) {
        if (head == null) return null;
        
        ListNode slow = head;
        ListNode fast = head;
        ListNode prev = null;
        
        while (fast != null && fast.next != null) {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        
        return fast == null ? prev : slow;
    }
    
    public static int getMiddleValue(ListNode head) {
        ListNode middle = findMiddle(head);
        return middle != null ? middle.val : -1;
    }
    
    public static ListNode[] splitAtMiddle(ListNode head) {
        if (head == null) return new ListNode[]{null, null};
        
        ListNode slow = head;
        ListNode fast = head;
        ListNode prev = null;
        
        while (fast != null && fast.next != null) {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        
        if (prev != null) {
            prev.next = null;
        }
        
        return new ListNode[]{head, slow};
    }
}
```

### 11. Reverse LinkedList (Iterative)
**Problem:** Reverse the LinkedList iteratively.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class ReverseLinkedList {
    public static ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode current = head;
        
        while (current != null) {
            ListNode nextTemp = current.next;
            current.next = prev;
            prev = current;
            current = nextTemp;
        }
        
        return prev;
    }
    
    public static ListNode reverseWithThreePointers(ListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        ListNode first = head;
        ListNode second = head.next;
        ListNode third;
        
        first.next = null;
        
        while (second != null) {
            third = second.next;
            second.next = first;
            first = second;
            second = third;
        }
        
        return first;
    }
    
    public static ListNode reverseInPlace(ListNode head) {
        if (head == null || head.next == null) return head;
        
        ListNode prev = null;
        ListNode curr = head;
        
        while (curr != null) {
            ListNode next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        
        return prev;
    }
}
```

### 12. Reverse LinkedList (Recursive)
**Problem:** Reverse LinkedList using recursion.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n) - recursion stack

```java
public class ReverseLinkedListRecursive {
    public static ListNode reverseList(ListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        ListNode newHead = reverseList(head.next);
        head.next.next = head;
        head.next = null;
        
        return newHead;
    }
    
    public static ListNode reverseRecursiveAlternative(ListNode head) {
        return reverseHelper(head, null);
    }
    
    private static ListNode reverseHelper(ListNode head, ListNode prev) {
        if (head == null) {
            return prev;
        }
        
        ListNode next = head.next;
        head.next = prev;
        
        return reverseHelper(next, head);
    }
    
    public static ListNode reverseRecursiveWithReturn(ListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        ListNode rest = reverseRecursiveWithReturn(head.next);
        
        head.next.next = head;
        head.next = null;
        
        return rest;
    }
}
```

### 13. Detect Loop in LinkedList
**Problem:** Check if LinkedList has a cycle.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class DetectLoop {
    public static boolean hasCycle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            
            if (slow == fast) {
                return true;
            }
        }
        
        return false;
    }
    
    public static boolean hasCycleHashSet(ListNode head) {
        Set<ListNode> visited = new HashSet<>();
        
        ListNode current = head;
        while (current != null) {
            if (visited.contains(current)) {
                return true;
            }
            visited.add(current);
            current = current.next;
        }
        
        return false;
    }
    
    public static boolean hasCycleModify(ListNode head) {
        ListNode current = head;
        
        while (current != null && current.next != null) {
            if (current.next == head) {
                return true;
            }
            
            ListNode nextNode = current.next;
            current.next = head;
            current = nextNode;
        }
        
        return false;
    }
    
    public static ListNode detectCycleNode(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            
            if (slow == fast) {
                break;
            }
        }
        
        if (fast == null || fast.next == null) {
            return null;
        }
        
        slow = head;
        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }
        
        return slow;
    }
}
```

### 14. Find Starting Point of Loop
**Problem:** Find where the cycle begins in LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LoopStartingPoint {
    public static ListNode detectCycle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            
            if (slow == fast) {
                break;
            }
        }
        
        if (fast == null || fast.next == null) {
            return null;
        }
        
        slow = head;
        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }
        
        return slow;
    }
    
    public static ListNode findLoopStart(ListNode head) {
        if (head == null || head.next == null) return null;
        
        ListNode intersection = getIntersection(head);
        if (intersection == null) return null;
        
        ListNode ptr1 = head;
        ListNode ptr2 = intersection;
        
        while (ptr1 != ptr2) {
            ptr1 = ptr1.next;
            ptr2 = ptr2.next;
        }
        
        return ptr1;
    }
    
    private static ListNode getIntersection(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            
            if (slow == fast) {
                return slow;
            }
        }
        
        return null;
    }
    
    public static int getLoopStartPosition(ListNode head) {
        ListNode loopStart = detectCycle(head);
        if (loopStart == null) return -1;
        
        int position = 0;
        ListNode current = head;
        
        while (current != loopStart) {
            current = current.next;
            position++;
        }
        
        return position;
    }
}
```

### 15. Length of Loop in LinkedList
**Problem:** Find the length of cycle in LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class LoopLength {
    public static int lengthOfLoop(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            
            if (slow == fast) {
                return countLoopNodes(slow);
            }
        }
        
        return 0;
    }
    
    private static int countLoopNodes(ListNode loopNode) {
        int count = 1;
        ListNode current = loopNode.next;
        
        while (current != loopNode) {
            count++;
            current = current.next;
        }
        
        return count;
    }
    
    public static int getLoopInfo(ListNode head) {
        ListNode intersection = getIntersection(head);
        if (intersection == null) return 0;
        
        int loopLength = 1;
        ListNode current = intersection.next;
        
        while (current != intersection) {
            loopLength++;
            current = current.next;
        }
        
        return loopLength;
    }
    
    private static ListNode getIntersection(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            
            if (slow == fast) {
                return slow;
            }
        }
        
        return null;
    }
    
    public static boolean hasLoopOfLengthK(ListNode head, int k) {
        return lengthOfLoop(head) == k;
    }
}
```

### 16. Check if LinkedList is Palindrome
**Problem:** Check if LinkedList reads same forwards and backwards.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class LinkedListPalindrome {
    public static boolean isPalindrome(ListNode head) {
        if (head == null || head.next == null) return true;
        
        ListNode middle = findMiddle(head);
        ListNode secondHalf = reverseList(middle.next);
        
        ListNode firstHalf = head;
        ListNode secondHalfCopy = secondHalf;
        
        boolean isPalin = true;
        while (isPalin && secondHalf != null) {
            if (firstHalf.val != secondHalf.val) {
                isPalin = false;
            }
            firstHalf = firstHalf.next;
            secondHalf = secondHalf.next;
        }
        
        middle.next = reverseList(secondHalfCopy);
        
        return isPalin;
    }
    
    private static ListNode findMiddle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast.next != null && fast.next.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        
        return slow;
    }
    
    private static ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode current = head;
        
        while (current != null) {
            ListNode nextTemp = current.next;
            current.next = prev;
            prev = current;
            current = nextTemp;
        }
        
        return prev;
    }
    
    public static boolean isPalindromeStack(ListNode head) {
        Stack<Integer> stack = new Stack<>();
        ListNode current = head;
        
        while (current != null) {
            stack.push(current.val);
            current = current.next;
        }
        
        current = head;
        while (current != null) {
            if (current.val != stack.pop()) {
                return false;
            }
            current = current.next;
        }
        
        return true;
    }
    
    public static boolean isPalindromeRecursive(ListNode head) {
        return isPalindromeHelper(head, head).isPalindrome;
    }
    
    private static class PalindromeResult {
        ListNode node;
        boolean isPalindrome;
        
        PalindromeResult(ListNode node, boolean isPalindrome) {
            this.node = node;
            this.isPalindrome = isPalindrome;
        }
    }
    
    private static PalindromeResult isPalindromeHelper(ListNode head, ListNode node) {
        if (node == null) {
            return new PalindromeResult(head, true);
        }
        
        PalindromeResult result = isPalindromeHelper(head, node.next);
        
        if (!result.isPalindrome || result.node.val != node.val) {
            return new PalindromeResult(result.node, false);
        }
        
        return new PalindromeResult(result.node.next, true);
    }
}
```

### 17. Segregate Odd and Even Nodes
**Problem:** Group odd and even positioned nodes together.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class OddEvenList {
    public static ListNode oddEvenList(ListNode head) {
        if (head == null || head.next == null) return head;
        
        ListNode odd = head;
        ListNode even = head.next;
        ListNode evenHead = even;
        
        while (even != null && even.next != null) {
            odd.next = even.next;
            odd = odd.next;
            
            even.next = odd.next;
            even = even.next;
        }
        
        odd.next = evenHead;
        
        return head;
    }
    
    public static ListNode segregateOddEvenValues(ListNode head) {
        if (head == null) return null;
        
        ListNode oddHead = null, oddTail = null;
        ListNode evenHead = null, evenTail = null;
        ListNode current = head;
        
        while (current != null) {
            if (current.val % 2 == 0) {
                if (evenHead == null) {
                    evenHead = evenTail = current;
                } else {
                    evenTail.next = current;
                    evenTail = current;
                }
            } else {
                if (oddHead == null) {
                    oddHead = oddTail = current;
                } else {
                    oddTail.next = current;
                    oddTail = current;
                }
            }
            current = current.next;
        }
        
        if (oddHead == null) return evenHead;
        if (evenHead == null) return oddHead;
        
        oddTail.next = evenHead;
        evenTail.next = null;
        
        return oddHead;
    }
    
    public static ListNode rearrangeOddEven(ListNode head) {
        if (head == null || head.next == null) return head;
        
        ListNode oddDummy = new ListNode(0);
        ListNode evenDummy = new ListNode(0);
        ListNode oddTail = oddDummy;
        ListNode evenTail = evenDummy;
        
        boolean isOdd = true;
        ListNode current = head;
        
        while (current != null) {
            if (isOdd) {
                oddTail.next = current;
                oddTail = current;
            } else {
                evenTail.next = current;
                evenTail = current;
            }
            
            current = current.next;
            isOdd = !isOdd;
        }
        
        evenTail.next = null;
        oddTail.next = evenDummy.next;
        
        return oddDummy.next;
    }
}
```

### 18. Remove Nth Node from End
**Problem:** Remove nth node from the end of LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class RemoveNthFromEnd {
    public static ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        
        ListNode first = dummy;
        ListNode second = dummy;
        
        for (int i = 1; i <= n + 1; i++) {
            first = first.next;
        }
        
        while (first != null) {
            first = first.next;
            second = second.next;
        }
        
        second.next = second.next.next;
        
        return dummy.next;
    }
    
    public static ListNode removeNthFromEndTwoPass(ListNode head, int n) {
        int length = getLength(head);
        int positionFromStart = length - n;
        
        if (positionFromStart == 0) {
            return head.next;
        }
        
        ListNode current = head;
        for (int i = 0; i < positionFromStart - 1; i++) {
            current = current.next;
        }
        
        current.next = current.next.next;
        
        return head;
    }
    
    private static int getLength(ListNode head) {
        int length = 0;
        while (head != null) {
            length++;
            head = head.next;
        }
        return length;
    }
    
    public static ListNode removeNthFromEndRecursive(ListNode head, int n) {
        return removeNthHelper(head, n).node;
    }
    
    private static class RemoveResult {
        ListNode node;
        int count;
        
        RemoveResult(ListNode node, int count) {
            this.node = node;
            this.count = count;
        }
    }
    
    private static RemoveResult removeNthHelper(ListNode head, int n) {
        if (head == null) {
            return new RemoveResult(null, 0);
        }
        
        RemoveResult result = removeNthHelper(head.next, n);
        result.count++;
        
        if (result.count == n) {
            return new RemoveResult(head.next, result.count);
        }
        
        head.next = result.node;
        return new RemoveResult(head, result.count);
    }
}
```

### 19. Delete Middle Node of LinkedList
**Problem:** Delete middle node of LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class DeleteMiddleNode {
    public static ListNode deleteMiddle(ListNode head) {
        if (head == null || head.next == null) return null;
        
        ListNode slow = head;
        ListNode fast = head;
        ListNode prev = null;
        
        while (fast != null && fast.next != null) {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        
        prev.next = slow.next;
        
        return head;
    }
    
    public static ListNode deleteMiddleAlternative(ListNode head) {
        if (head == null || head.next == null) return null;
        
        int length = getLength(head);
        int middleIndex = length / 2;
        
        if (middleIndex == 0) {
            return head.next;
        }
        
        ListNode current = head;
        for (int i = 0; i < middleIndex - 1; i++) {
            current = current.next;
        }
        
        current.next = current.next.next;
        
        return head;
    }
    
    private static int getLength(ListNode head) {
        int length = 0;
        while (head != null) {
            length++;
            head = head.next;
        }
        return length;
    }
    
    public static ListNode deleteKthNode(ListNode head, int k) {
        if (head == null) return null;
        
        if (k == 1) {
            return head.next;
        }
        
        ListNode current = head;
        for (int i = 1; i < k - 1 && current != null; i++) {
            current = current.next;
        }
        
        if (current != null && current.next != null) {
            current.next = current.next.next;
        }
        
        return head;
    }
}
```

### 20. Sort LinkedList
**Problem:** Sort LinkedList using merge sort.  
**Time Complexity:** O(n log n)  
**Space Complexity:** O(log n) - recursion stack

```java
public class SortLinkedList {
    public static ListNode sortList(ListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        ListNode middle = getMiddle(head);
        ListNode nextOfMiddle = middle.next;
        middle.next = null;
        
        ListNode left = sortList(head);
        ListNode right = sortList(nextOfMiddle);
        
        return merge(left, right);
    }
    
    private static ListNode getMiddle(ListNode head) {
        if (head == null) return head;
        
        ListNode slow = head;
        ListNode fast = head;
        ListNode prev = null;
        
        while (fast != null && fast.next != null) {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        
        return prev;
    }
    
    private static ListNode merge(ListNode a, ListNode b) {
        if (a == null) return b;
        if (b == null) return a;
        
        ListNode result;
        
        if (a.val <= b.val) {
            result = a;
            result.next = merge(a.next, b);
        } else {
            result = b;
            result.next = merge(a, b.next);
        }
        
        return result;
    }
    
    public static ListNode sortListIterative(ListNode head) {
        if (head == null || head.next == null) return head;
        
        int length = getLength(head);
        
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        
        for (int size = 1; size < length; size *= 2) {
            ListNode prev = dummy;
            ListNode current = dummy.next;
            
            while (current != null) {
                ListNode left = current;
                ListNode right = split(left, size);
                current = split(right, size);
                
                prev.next = mergeIterative(left, right);
                
                while (prev.next != null) {
                    prev = prev.next;
                }
            }
        }
        
        return dummy.next;
    }
    
    private static ListNode split(ListNode head, int size) {
        for (int i = 1; head != null && i < size; i++) {
            head = head.next;
        }
        
        if (head == null) return null;
        
        ListNode next = head.next;
        head.next = null;
        return next;
    }
    
    private static ListNode mergeIterative(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        
        while (l1 != null && l2 != null) {
            if (l1.val <= l2.val) {
                current.next = l1;
                l1 = l1.next;
            } else {
                current.next = l2;
                l2 = l2.next;
            }
            current = current.next;
        }
        
        current.next = (l1 != null) ? l1 : l2;
        
        return dummy.next;
    }
    
    private static int getLength(ListNode head) {
        int length = 0;
        while (head != null) {
            length++;
            head = head.next;
        }
        return length;
    }
}
```

### 21. Sort LinkedList of 0s, 1s, and 2s
**Problem:** Sort LinkedList containing only 0, 1, and 2.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class Sort012LinkedList {
    public static ListNode sortList(ListNode head) {
        if (head == null || head.next == null) return head;
        
        ListNode zeroHead = new ListNode(0);
        ListNode oneHead = new ListNode(0);
        ListNode twoHead = new ListNode(0);
        
        ListNode zero = zeroHead;
        ListNode one = oneHead;
        ListNode two = twoHead;
        
        ListNode current = head;
        
        while (current != null) {
            if (current.val == 0) {
                zero.next = current;
                zero = zero.next;
            } else if (current.val == 1) {
                one.next = current;
                one = one.next;
            } else {
                two.next = current;
                two = two.next;
            }
            current = current.next;
        }
        
        zero.next = (oneHead.next != null) ? oneHead.next : twoHead.next;
        one.next = twoHead.next;
        two.next = null;
        
        ListNode newHead = zeroHead.next;
        return newHead;
    }
    
    public static ListNode sortListByCount(ListNode head) {
        int[] count = new int[3];
        ListNode current = head;
        
        while (current != null) {
            count[current.val]++;
            current = current.next;
        }
        
        current = head;
        int i = 0;
        
        while (current != null) {
            if (count[i] == 0) {
                i++;
            } else {
                current.val = i;
                count[i]--;
                current = current.next;
            }
        }
        
        return head;
    }
    
    public static ListNode sortListInPlace(ListNode head) {
        if (head == null) return head;
        
        ListNode current = head;
        ListNode zeroTail = null;
        ListNode oneTail = null;
        
        while (current != null) {
            if (current.val == 0) {
                if (zeroTail == null) {
                    if (oneTail != null) {
                        ListNode temp = current.next;
                        current.next = head;
                        oneTail.next = temp;
                        head = current;
                        current = temp;
                    } else {
                        zeroTail = current;
                        current = current.next;
                    }
                } else {
                    zeroTail = current;
                    current = current.next;
                }
            } else if (current.val == 1) {
                if (oneTail == null) {
                    oneTail = current;
                }
                current = current.next;
            } else {
                current = current.next;
            }
        }
        
        return head;
    }
}
```

### 22. Find Intersection Point of Two LinkedLists
**Problem:** Find node where two LinkedLists intersect.  
**Time Complexity:** O(n + m)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class IntersectionOfLinkedLists {
    public static ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        if (headA == null || headB == null) return null;
        
        ListNode pointerA = headA;
        ListNode pointerB = headB;
        
        while (pointerA != pointerB) {
            pointerA = (pointerA == null) ? headB : pointerA.next;
            pointerB = (pointerB == null) ? headA : pointerB.next;
        }
        
        return pointerA;
    }
    
    public static ListNode getIntersectionNodeLength(ListNode headA, ListNode headB) {
        int lenA = getLength(headA);
        int lenB = getLength(headB);
        
        ListNode currentA = headA;
        ListNode currentB = headB;
        
        int diff = Math.abs(lenA - lenB);
        
        if (lenA > lenB) {
            for (int i = 0; i < diff; i++) {
                currentA = currentA.next;
            }
        } else {
            for (int i = 0; i < diff; i++) {
                currentB = currentB.next;
            }
        }
        
        while (currentA != null && currentB != null) {
            if (currentA == currentB) {
                return currentA;
            }
            currentA = currentA.next;
            currentB = currentB.next;
        }
        
        return null;
    }
    
    private static int getLength(ListNode head) {
        int length = 0;
        while (head != null) {
            length++;
            head = head.next;
        }
        return length;
    }
    
    public static ListNode getIntersectionNodeHashSet(ListNode headA, ListNode headB) {
        Set<ListNode> visitedNodes = new HashSet<>();
        
        ListNode current = headA;
        while (current != null) {
            visitedNodes.add(current);
            current = current.next;
        }
        
        current = headB;
        while (current != null) {
            if (visitedNodes.contains(current)) {
                return current;
            }
            current = current.next;
        }
        
        return null;
    }
    
    public static ListNode getIntersectionNodeStack(ListNode headA, ListNode headB) {
        Stack<ListNode> stackA = new Stack<>();
        Stack<ListNode> stackB = new Stack<>();
        
        ListNode current = headA;
        while (current != null) {
            stackA.push(current);
            current = current.next;
        }
        
        current = headB;
        while (current != null) {
            stackB.push(current);
            current = current.next;
        }
        
        ListNode intersection = null;
        while (!stackA.isEmpty() && !stackB.isEmpty() && stackA.peek() == stackB.peek()) {
            intersection = stackA.pop();
            stackB.pop();
        }
        
        return intersection;
    }
}
```

### 23. Add 1 to Number Represented by LinkedList
**Problem:** Add 1 to number represented as LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class AddOneToLinkedList {
    public static ListNode addOne(ListNode head) {
        head = reverse(head);
        
        ListNode current = head;
        int carry = 1;
        
        while (current != null && carry > 0) {
            int sum = current.val + carry;
            current.val = sum % 10;
            carry = sum / 10;
            
            if (carry > 0 && current.next == null) {
                current.next = new ListNode(0);
            }
            
            current = current.next;
        }
        
        return reverse(head);
    }
    
    private static ListNode reverse(ListNode head) {
        ListNode prev = null;
        ListNode current = head;
        
        while (current != null) {
            ListNode next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }
        
        return prev;
    }
    
    public static ListNode addOneRecursive(ListNode head) {
        int carry = addOneHelper(head);
        
        if (carry == 1) {
            ListNode newHead = new ListNode(1);
            newHead.next = head;
            return newHead;
        }
        
        return head;
    }
    
    private static int addOneHelper(ListNode head) {
        if (head == null) return 1;
        
        int carry = addOneHelper(head.next);
        int sum = head.val + carry;
        
        head.val = sum % 10;
        return sum / 10;
    }
    
    public static ListNode addOneIterativeBacktrack(ListNode head) {
        ListNode current = head;
        ListNode lastNonNine = null;
        
        while (current != null) {
            if (current.val != 9) {
                lastNonNine = current;
            }
            current = current.next;
        }
        
        if (lastNonNine == null) {
            ListNode newHead = new ListNode(1);
            newHead.next = head;
            current = head;
            while (current != null) {
                current.val = 0;
                current = current.next;
            }
            return newHead;
        }
        
        lastNonNine.val++;
        current = lastNonNine.next;
        while (current != null) {
            current.val = 0;
            current = current.next;
        }
        
        return head;
    }
}
```

### 24. Add Two Numbers Represented by LinkedList
**Problem:** Add two numbers represented as LinkedLists.  
**Time Complexity:** O(max(n, m))  
**Space Complexity:** O(max(n, m))

```java
public class AddTwoNumbers {
    public static ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        int carry = 0;
        
        while (l1 != null || l2 != null || carry != 0) {
            int val1 = (l1 != null) ? l1.val : 0;
            int val2 = (l2 != null) ? l2.val : 0;
            
            int sum = val1 + val2 + carry;
            carry = sum / 10;
            
            current.next = new ListNode(sum % 10);
            current = current.next;
            
            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }
        
        return dummy.next;
    }
    
    public static ListNode addTwoNumbersReverse(ListNode l1, ListNode l2) {
        l1 = reverse(l1);
        l2 = reverse(l2);
        
        ListNode result = addTwoNumbers(l1, l2);
        
        return reverse(result);
    }
    
    private static ListNode reverse(ListNode head) {
        ListNode prev = null;
        ListNode current = head;
        
        while (current != null) {
            ListNode next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }
        
        return prev;
    }
    
    public static ListNode addTwoNumbersRecursive(ListNode l1, ListNode l2) {
        return addHelper(l1, l2, 0);
    }
    
    private static ListNode addHelper(ListNode l1, ListNode l2, int carry) {
        if (l1 == null && l2 == null && carry == 0) {
            return null;
        }
        
        int val1 = (l1 != null) ? l1.val : 0;
        int val2 = (l2 != null) ? l2.val : 0;
        
        int sum = val1 + val2 + carry;
        
        ListNode result = new ListNode(sum % 10);
        
        ListNode next1 = (l1 != null) ? l1.next : null;
        ListNode next2 = (l2 != null) ? l2.next : null;
        
        result.next = addHelper(next1, next2, sum / 10);
        
        return result;
    }
}
```

### 25. Delete All Occurrences of Key in DLL
**Problem:** Remove all nodes with given key from DLL.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class DeleteAllOccurrencesDLL {
    public static DoublyListNode deleteAllOccurrences(DoublyListNode head, int key) {
        DoublyListNode current = head;
        
        while (current != null) {
            if (current.val == key) {
                if (current.prev != null) {
                    current.prev.next = current.next;
                } else {
                    head = current.next;
                }
                
                if (current.next != null) {
                    current.next.prev = current.prev;
                }
                
                DoublyListNode next = current.next;
                current = next;
            } else {
                current = current.next;
            }
        }
        
        return head;
    }
    
    public static DoublyListNode deleteAllOccurrencesRecursive(DoublyListNode head, int key) {
        if (head == null) return null;
        
        if (head.val == key) {
            DoublyListNode newHead = head.next;
            if (newHead != null) {
                newHead.prev = null;
            }
            return deleteAllOccurrencesRecursive(newHead, key);
        }
        
        head.next = deleteAllOccurrencesRecursive(head.next, key);
        if (head.next != null) {
            head.next.prev = head;
        }
        
        return head;
    }
}
```

### 26. Find Pairs with Given Sum in DLL
**Problem:** Find all pairs in DLL that sum to target.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class FindPairsDLL {
    public static List<int[]> findPairsWithSum(DoublyListNode head, int target) {
        List<int[]> pairs = new ArrayList<>();
        
        if (head == null) return pairs;
        
        DoublyListNode left = head;
        DoublyListNode right = getTail(head);
        
        while (left != right && left.prev != right) {
            int sum = left.val + right.val;
            
            if (sum == target) {
                pairs.add(new int[]{left.val, right.val});
                left = left.next;
                right = right.prev;
            } else if (sum < target) {
                left = left.next;
            } else {
                right = right.prev;
            }
        }
        
        return pairs;
    }
    
    private static DoublyListNode getTail(DoublyListNode head) {
        while (head.next != null) {
            head = head.next;
        }
        return head;
    }
    
    public static boolean findPairExists(DoublyListNode head, int target) {
        if (head == null) return false;
        
        DoublyListNode left = head;
        DoublyListNode right = getTail(head);
        
        while (left != right && left.prev != right) {
            int sum = left.val + right.val;
            
            if (sum == target) {
                return true;
            } else if (sum < target) {
                left = left.next;
            } else {
                right = right.prev;
            }
        }
        
        return false;
    }
    
    public static int countPairsWithSum(DoublyListNode head, int target) {
        int count = 0;
        
        if (head == null) return count;
        
        DoublyListNode left = head;
        DoublyListNode right = getTail(head);
        
        while (left != right && left.prev != right) {
            int sum = left.val + right.val;
            
            if (sum == target) {
                count++;
                left = left.next;
                right = right.prev;
            } else if (sum < target) {
                left = left.next;
            } else {
                right = right.prev;
            }
        }
        
        return count;
    }
}
```

### 27. Remove Duplicates from Sorted DLL
**Problem:** Remove duplicate nodes from sorted DLL.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class RemoveDuplicatesDLL {
    public static DoublyListNode removeDuplicates(DoublyListNode head) {
        if (head == null || head.next == null) return head;
        
        DoublyListNode current = head;
        
        while (current.next != null) {
            if (current.val == current.next.val) {
                DoublyListNode duplicate = current.next;
                current.next = duplicate.next;
                
                if (duplicate.next != null) {
                    duplicate.next.prev = current;
                }
            } else {
                current = current.next;
            }
        }
        
        return head;
    }
    
    public static DoublyListNode removeDuplicatesRecursive(DoublyListNode head) {
        if (head == null || head.next == null) return head;
        
        head.next = removeDuplicatesRecursive(head.next);
        
        if (head.next != null && head.val == head.next.val) {
            DoublyListNode next = head.next;
            head.next = next.next;
            if (next.next != null) {
                next.next.prev = head;
            }
        } else if (head.next != null) {
            head.next.prev = head;
        }
        
        return head;
    }
    
    public static DoublyListNode removeAllDuplicates(DoublyListNode head) {
        DoublyListNode dummy = new DoublyListNode(0);
        dummy.next = head;
        if (head != null) head.prev = dummy;
        
        DoublyListNode prev = dummy;
        DoublyListNode current = head;
        
        while (current != null) {
            if (current.next != null && current.val == current.next.val) {
                int duplicateVal = current.val;
                
                while (current != null && current.val == duplicateVal) {
                    DoublyListNode next = current.next;
                    current = next;
                }
                
                prev.next = current;
                if (current != null) {
                    current.prev = prev;
                }
            } else {
                prev = current;
                current = current.next;
            }
        }
        
        DoublyListNode result = dummy.next;
        if (result != null) {
            result.prev = null;
        }
        
        return result;
    }
}
```

### 28. Reverse LinkedList in Groups of K
**Problem:** Reverse every k nodes in LinkedList.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class ReverseKGroup {
    public static ListNode reverseKGroup(ListNode head, int k) {
        ListNode current = head;
        int count = 0;
        
        while (current != null && count != k) {
            current = current.next;
            count++;
        }
        
        if (count == k) {
            current = reverseKGroup(current, k);
            
            while (count-- > 0) {
                ListNode temp = head.next;
                head.next = current;
                current = head;
                head = temp;
            }
            head = current;
        }
        
        return head;
    }
    
    public static ListNode reverseKGroupIterative(ListNode head, int k) {
        if (head == null || k == 1) return head;
        
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode prevGroupEnd = dummy;
        
        while (true) {
            ListNode kthNode = getKthNode(prevGroupEnd, k);
            if (kthNode == null) break;
            
            ListNode nextGroupStart = kthNode.next;
            
            ListNode prev = nextGroupStart;
            ListNode current = prevGroupEnd.next;
            
            while (current != nextGroupStart) {
                ListNode next = current.next;
                current.next = prev;
                prev = current;
                current = next;
            }
            
            ListNode temp = prevGroupEnd.next;
            prevGroupEnd.next = kthNode;
            prevGroupEnd = temp;
        }
        
        return dummy.next;
    }
    
    private static ListNode getKthNode(ListNode start, int k) {
        while (start != null && k > 0) {
            start = start.next;
            k--;
        }
        return start;
    }
    
    public static ListNode reverseAlternateKGroup(ListNode head, int k) {
        ListNode current = head;
        int count = 0;
        
        while (current != null && count < k) {
            current = current.next;
            count++;
        }
        
        if (count == k) {
            current = reverseAlternateKGroup(current, k);
            
            while (count-- > 0) {
                ListNode temp = head.next;
                head.next = current;
                current = head;
                head = temp;
            }
            head = current;
            
            count = 0;
            while (count < k && head != null) {
                head = head.next;
                count++;
            }
        }
        
        return head;
    }
}
```

### 29. Rotate LinkedList
**Problem:** Rotate LinkedList to the right by k places.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class RotateLinkedList {
    public static ListNode rotateRight(ListNode head, int k) {
        if (head == null || head.next == null || k == 0) return head;
        
        int length = 1;
        ListNode tail = head;
        while (tail.next != null) {
            tail = tail.next;
            length++;
        }
        
        k = k % length;
        if (k == 0) return head;
        
        tail.next = head;
        
        int stepsToNewTail = length - k;
        ListNode newTail = head;
        for (int i = 1; i < stepsToNewTail; i++) {
            newTail = newTail.next;
        }
        
        ListNode newHead = newTail.next;
        newTail.next = null;
        
        return newHead;
    }
    
    public static ListNode rotateLeft(ListNode head, int k) {
        if (head == null || head.next == null || k == 0) return head;
        
        int length = getLength(head);
        k = k % length;
        if (k == 0) return head;
        
        ListNode current = head;
        for (int i = 1; i < k; i++) {
            current = current.next;
        }
        
        ListNode newHead = current.next;
        current.next = null;
        
        ListNode tail = newHead;
        while (tail.next != null) {
            tail = tail.next;
        }
        tail.next = head;
        
        return newHead;
    }
    
    private static int getLength(ListNode head) {
        int length = 0;
        while (head != null) {
            length++;
            head = head.next;
        }
        return length;
    }
    
    public static ListNode rotateByNodes(ListNode head, int k) {
        if (head == null || head.next == null) return head;
        
        ListNode fast = head;
        ListNode slow = head;
        
        for (int i = 0; i < k; i++) {
            if (fast == null) return head;
            fast = fast.next;
        }
        
        if (fast == null) return head;
        
        while (fast.next != null) {
            fast = fast.next;
            slow = slow.next;
        }
        
        fast.next = head;
        ListNode newHead = slow.next;
        slow.next = null;
        
        return newHead;
    }
}
```

### 30. Flatten LinkedList
**Problem:** Flatten multilevel LinkedList with down pointers.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
public class FlattenLinkedList {
    static class Node {
        int val;
        Node next;
        Node down;
        
        Node(int val) {
            this.val = val;
        }
    }
    
    public static Node flatten(Node head) {
        if (head == null) return null;
        
        Node current = head;
        
        while (current != null) {
            if (current.down != null) {
                Node next = current.next;
                Node downTail = getTail(current.down);
                
                current.next = current.down;
                current.down = null;
                
                downTail.next = next;
            }
            current = current.next;
        }
        
        return head;
    }
    
    private static Node getTail(Node head) {
        while (head.next != null) {
            head = head.next;
        }
        return head;
    }
    
    public static Node flattenSorted(Node head) {
        if (head == null || head.next == null) return head;
        
        head.next = flattenSorted(head.next);
        
        head = merge(head, head.next);
        
        return head;
    }
    
    private static Node merge(Node a, Node b) {
        if (a == null) return b;
        if (b == null) return a;
        
        Node result;
        
        if (a.val < b.val) {
            result = a;
            result.down = merge(a.down, b);
        } else {
            result = b;
            result.down = merge(a, b.down);
        }
        
        result.next = null;
        return result;
    }
    
    public static Node flattenIterative(Node head) {
        if (head == null) return null;
        
        Node dummy = new Node(0);
        Node current = dummy;
        
        java.util.Stack<Node> stack = new java.util.Stack<>();
        stack.push(head);
        
        while (!stack.isEmpty()) {
            Node node = stack.pop();
            
            if (node.next != null) {
                stack.push(node.next);
            }
            if (node.down != null) {
                stack.push(node.down);
            }
            
            current.next = node;
            node.down = null;
            current = node;
        }
        
        return dummy.next;
    }
}
```

### 31. Clone LinkedList with Random Pointers
**Problem:** Deep copy LinkedList with random pointers.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class CloneRandomList {
    static class Node {
        int val;
        Node next;
        Node random;
        
        Node(int val) {
            this.val = val;
        }
    }
    
    public static Node copyRandomList(Node head) {
        if (head == null) return null;
        
        Node current = head;
        while (current != null) {
            Node clone = new Node(current.val);
            clone.next = current.next;
            current.next = clone;
            current = clone.next;
        }
        
        current = head;
        while (current != null) {
            if (current.random != null) {
                current.next.random = current.random.next;
            }
            current = current.next.next;
        }
        
        Node dummy = new Node(0);
        Node cloneCurrent = dummy;
        current = head;
        
        while (current != null) {
            cloneCurrent.next = current.next;
            current.next = current.next.next;
            current = current.next;
            cloneCurrent = cloneCurrent.next;
        }
        
        return dummy.next;
    }
    
    public static Node copyRandomListHashMap(Node head) {
        if (head == null) return null;
        
        Map<Node, Node> map = new HashMap<>();
        
        Node current = head;
        while (current != null) {
            map.put(current, new Node(current.val));
            current = current.next;
        }
        
        current = head;
        while (current != null) {
            map.get(current).next = map.get(current.next);
            map.get(current).random = map.get(current.random);
            current = current.next;
        }
        
        return map.get(head);
    }
    
    public static Node copyRandomListRecursive(Node head) {
        Map<Node, Node> visited = new HashMap<>();
        return cloneHelper(head, visited);
    }
    
    private static Node cloneHelper(Node node, Map<Node, Node> visited) {
        if (node == null) return null;
        
        if (visited.containsKey(node)) {
            return visited.get(node);
        }
        
        Node clone = new Node(node.val);
        visited.put(node, clone);
        
        clone.next = cloneHelper(node.next, visited);
        clone.random = cloneHelper(node.random, visited);
        
        return clone;
    }
}
```

---



## Recursion

```java
public class RecursionFundamentals {
    public static returnType recursiveFunction(parameters) {
        // Base case
        if (baseCondition) {
            return baseResult;
        }
        
        // Recursive case
        returnType result = recursiveFunction(modifiedParameters);

        return result;
    }
}
```


### 1. Print N to 1 Using Recursion
**Problem:** Print numbers from N to 1 using recursion.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n) - recursion stack

```java
public class PrintNto1 {
    public static void printNto1(int n) {
        if (n < 1) {
            return;
        }
        
        System.out.print(n + " ");
        printNto1(n - 1);
    }
    
    public static void printNto1Tail(int n) {
        if (n < 1) {
            return;
        }
        
        System.out.print(n + " ");
        printNto1Tail(n - 1);
    }
    
    public static void print1toNThenNto1(int n) {
        if (n < 1) {
            return;
        }
        
        System.out.print(n + " ");
        print1toNThenNto1(n - 1);
        System.out.print(n + " ");
    }
}
```

### 2. Print 1 to N Using Recursion
**Problem:** Print numbers from 1 to N using recursion.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class Print1toN {
    public static void print1toN(int n) {
        if (n < 1) {
            return;
        }
        
        print1toN(n - 1);
        System.out.print(n + " ");
    }
    
    public static void print1toNParameterized(int i, int n) {
        if (i > n) {
            return;
        }
        
        System.out.print(i + " ");
        print1toNParameterized(i + 1, n);
    }
    
    public static void print1toNBacktrack(int n) {
        if (n < 1) {
            return;
        }
        
        print1toNBacktrack(n - 1);
        System.out.print(n + " ");
    }
}
```

### 3. Sum of First N Numbers
**Problem:** Calculate sum of first N natural numbers.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class SumOfN {
    public static int sumOfN(int n) {
        if (n <= 0) {
            return 0;
        }
        
        return n + sumOfN(n - 1);
    }
    
    public static void sumOfNParameterized(int i, int sum) {
        if (i < 1) {
            System.out.println(sum);
            return;
        }
        
        sumOfNParameterized(i - 1, sum + i);
    }
    
    public static int sumOfNFunctional(int n) {
        if (n == 0) {
            return 0;
        }
        
        return n + sumOfNFunctional(n - 1);
    }
    
    public static int sumOfNTailRecursive(int n, int accumulator) {
        if (n == 0) {
            return accumulator;
        }
        
        return sumOfNTailRecursive(n - 1, accumulator + n);
    }
}
```

### 4. Factorial of N
**Problem:** Calculate factorial of N using recursion.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class FactorialN {
    public static long factorial(int n) {
        if (n <= 1) {
            return 1;
        }
        
        return n * factorial(n - 1);
    }
    
    public static long factorialTailRecursive(int n, long accumulator) {
        if (n <= 1) {
            return accumulator;
        }
        
        return factorialTailRecursive(n - 1, n * accumulator);
    }
    
    public static void factorialParameterized(int i, long fact) {
        if (i < 1) {
            System.out.println(fact);
            return;
        }
        
        factorialParameterized(i - 1, fact * i);
    }
    
    public static long factorialIterative(int n) {
        long result = 1;
        for (int i = 2; i <= n; i++) {
            result *= i;
        }
        return result;
    }
}
```

### 5. Reverse an Array Using Recursion
**Problem:** Reverse array elements using recursion.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class ReverseArray {
    public static void reverseArray(int[] arr, int start, int end) {
        if (start >= end) {
            return;
        }
        
        swap(arr, start, end);
        reverseArray(arr, start + 1, end - 1);
    }
    
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
    
    public static void reverseArraySinglePointer(int[] arr, int i) {
        int n = arr.length;
        if (i >= n / 2) {
            return;
        }
        
        swap(arr, i, n - i - 1);
        reverseArraySinglePointer(arr, i + 1);
    }
    
    public static int[] reverseArrayFunctional(int[] arr, int index) {
        if (index >= arr.length / 2) {
            return arr;
        }
        
        swap(arr, index, arr.length - 1 - index);
        return reverseArrayFunctional(arr, index + 1);
    }
    
    public static void reverseArrayHelper(int[] arr) {
        reverseArrayRecursive(arr, 0);
    }
    
    private static void reverseArrayRecursive(int[] arr, int index) {
        if (index >= arr.length / 2) {
            return;
        }
        
        int temp = arr[index];
        arr[index] = arr[arr.length - 1 - index];
        arr[arr.length - 1 - index] = temp;
        
        reverseArrayRecursive(arr, index + 1);
    }
}
```

### 6. Check if String is Palindrome
**Problem:** Check if string is palindrome using recursion.  
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

```java
public class StringPalindrome {
    public static boolean isPalindrome(String s, int i) {
        if (i >= s.length() / 2) {
            return true;
        }
        
        if (s.charAt(i) != s.charAt(s.length() - i - 1)) {
            return false;
        }
        
        return isPalindrome(s, i + 1);
    }
    
    public static boolean isPalindromeTwoPointer(String s, int left, int right) {
        if (left >= right) {
            return true;
        }
        
        if (s.charAt(left) != s.charAt(right)) {
            return false;
        }
        
        return isPalindromeTwoPointer(s, left + 1, right - 1);
    }
    
    public static boolean isPalindromeClean(String s) {
        return isPalindromeHelper(s.toLowerCase(), 0, s.length() - 1);
    }
    
    private static boolean isPalindromeHelper(String s, int left, int right) {
        if (left >= right) {
            return true;
        }
        
        if (!Character.isAlphaNumeric(s.charAt(left))) {
            return isPalindromeHelper(s, left + 1, right);
        }
        
        if (!Character.isAlphaNumeric(s.charAt(right))) {
            return isPalindromeHelper(s, left, right - 1);
        }
        
        if (s.charAt(left) != s.charAt(right)) {
            return false;
        }
        
        return isPalindromeHelper(s, left + 1, right - 1);
    }
}
```

### 7. Fibonacci Number
**Problem:** Calculate nth Fibonacci number using recursion.  
**Time Complexity:** O(2^n) naive, O(n) optimized  
**Space Complexity:** O(n)

```java
import java.util.*;

public class FibonacciNumber {
    public static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
    
    public static int fibonacciMemoized(int n, int[] memo) {
        if (n <= 1) {
            return n;
        }
        
        if (memo[n] != -1) {
            return memo[n];
        }
        
        memo[n] = fibonacciMemoized(n - 1, memo) + fibonacciMemoized(n - 2, memo);
        return memo[n];
    }
    
    public static int fibonacciMemoizedMap(int n, Map<Integer, Integer> memo) {
        if (n <= 1) {
            return n;
        }
        
        if (memo.containsKey(n)) {
            return memo.get(n);
        }
        
        int result = fibonacciMemoizedMap(n - 1, memo) + fibonacciMemoizedMap(n - 2, memo);
        memo.put(n, result);
        return result;
    }
    
    public static int fibonacciIterative(int n) {
        if (n <= 1) return n;
        
        int prev2 = 0, prev1 = 1;
        
        for (int i = 2; i <= n; i++) {
            int current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        
        return prev1;
    }
    
    public static int fibonacciOptimized(int n) {
        return fibonacciMemoized(n, new int[n + 1]);
    }
    
    static {
        Arrays.fill(new int[1000], -1);
    }
}
```

### 8. Multiple Recursion Calls
**Problem:** Understanding multiple recursive calls in single function.  
**Time Complexity:** Varies based on problem  
**Space Complexity:** O(depth)

```java
public class MultipleRecursionCalls {
    public static void printFibonacciSequence(int n) {
        if (n <= 0) return;
        
        if (n == 1) {
            System.out.print("0 ");
            return;
        }
        
        if (n == 2) {
            System.out.print("0 1 ");
            return;
        }
        
        printFibonacciSequence(n - 1);
        System.out.print((fibonacci(n - 1)) + " ");
    }
    
    private static int fibonacci(int n) {
        if (n <= 1) return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
    
    public static void towerOfHanoi(int n, char source, char destination, char auxiliary) {
        if (n == 1) {
            System.out.println("Move disk 1 from " + source + " to " + destination);
            return;
        }
        
        towerOfHanoi(n - 1, source, auxiliary, destination);
        System.out.println("Move disk " + n + " from " + source + " to " + destination);
        towerOfHanoi(n - 1, auxiliary, destination, source);
    }
    
    public static int ackermann(int m, int n) {
        if (m == 0) {
            return n + 1;
        } else if (m > 0 && n == 0) {
            return ackermann(m - 1, 1);
        } else {
            return ackermann(m - 1, ackermann(m, n - 1));
        }
    }
}
```

### 9. Print All Subsequences/Subsets
**Problem:** Generate all possible subsequences of array/string.  
**Time Complexity:** O(2^n)  
**Space Complexity:** O(n) - recursion depth

```java
import java.util.*;

public class PrintSubsequences {
    public static void printSubsequences(int[] arr, int index, List<Integer> current) {
        if (index == arr.length) {
            System.out.println(current);
            return;
        }
        
        current.add(arr[index]);
        printSubsequences(arr, index + 1, current);
        
        current.remove(current.size() - 1);
        printSubsequences(arr, index + 1, current);
    }
    
    public static List<List<Integer>> generateSubsequences(int[] arr) {
        List<List<Integer>> result = new ArrayList<>();
        generateSubsequencesHelper(arr, 0, new ArrayList<>(), result);
        return result;
    }
    
    private static void generateSubsequencesHelper(int[] arr, int index, 
                                                 List<Integer> current, 
                                                 List<List<Integer>> result) {
        if (index == arr.length) {
            result.add(new ArrayList<>(current));
            return;
        }
        
        current.add(arr[index]);
        generateSubsequencesHelper(arr, index + 1, current, result);
        
        current.remove(current.size() - 1);
        generateSubsequencesHelper(arr, index + 1, current, result);
    }
    
    public static void printStringSubsequences(String s, int index, String current) {
        if (index == s.length()) {
            System.out.println("\"" + current + "\"");
            return;
        }
        
        printStringSubsequences(s, index + 1, current + s.charAt(index));
        printStringSubsequences(s, index + 1, current);
    }
    
    public static List<String> generateStringSubsequences(String s) {
        List<String> result = new ArrayList<>();
        generateStringSubsequencesHelper(s, 0, "", result);
        return result;
    }
    
    private static void generateStringSubsequencesHelper(String s, int index, 
                                                       String current, 
                                                       List<String> result) {
        if (index == s.length()) {
            result.add(current);
            return;
        }
        
        generateStringSubsequencesHelper(s, index + 1, current + s.charAt(index), result);
        generateStringSubsequencesHelper(s, index + 1, current, result);
    }
}
```

### 10. Print Subsequences whose Sum = K
**Problem:** Print all subsequences with sum equal to K.  
**Time Complexity:** O(2^n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class SubsequencesSumK {
    public static void printSubsequencesWithSum(int[] arr, int index, 
                                               List<Integer> current, 
                                               int targetSum, int currentSum) {
        if (index == arr.length) {
            if (currentSum == targetSum) {
                System.out.println(current);
            }
            return;
        }
        
        current.add(arr[index]);
        printSubsequencesWithSum(arr, index + 1, current, targetSum, currentSum + arr[index]);
        
        current.remove(current.size() - 1);
        printSubsequencesWithSum(arr, index + 1, current, targetSum, currentSum);
    }
    
    public static List<List<Integer>> findSubsequencesWithSum(int[] arr, int targetSum) {
        List<List<Integer>> result = new ArrayList<>();
        findSubsequencesWithSumHelper(arr, 0, new ArrayList<>(), targetSum, 0, result);
        return result;
    }
    
    private static void findSubsequencesWithSumHelper(int[] arr, int index, 
                                                     List<Integer> current, 
                                                     int targetSum, int currentSum,
                                                     List<List<Integer>> result) {
        if (index == arr.length) {
            if (currentSum == targetSum) {
                result.add(new ArrayList<>(current));
            }
            return;
        }
        
        current.add(arr[index]);
        findSubsequencesWithSumHelper(arr, index + 1, current, targetSum, 
                                     currentSum + arr[index], result);
        
        current.remove(current.size() - 1);
        findSubsequencesWithSumHelper(arr, index + 1, current, targetSum, currentSum, result);
    }
    
    public static void printOptimizedSubsequencesWithSum(int[] arr, int index, 
                                                        List<Integer> current, 
                                                        int targetSum) {
        if (targetSum == 0) {
            System.out.println(current);
            return;
        }
        
        if (index == arr.length || targetSum < 0) {
            return;
        }
        
        current.add(arr[index]);
        printOptimizedSubsequencesWithSum(arr, index + 1, current, targetSum - arr[index]);
        
        current.remove(current.size() - 1);
        printOptimizedSubsequencesWithSum(arr, index + 1, current, targetSum);
    }
}
```

### 11. Count Subsequences with Sum K
**Problem:** Count number of subsequences with sum equal to K.  
**Time Complexity:** O(2^n)  
**Space Complexity:** O(n)

```java
public class CountSubsequencesSumK {
    public static int countSubsequencesWithSum(int[] arr, int index, int targetSum) {
        if (targetSum == 0) {
            return 1;
        }
        
        if (index == arr.length || targetSum < 0) {
            return 0;
        }
        
        int include = countSubsequencesWithSum(arr, index + 1, targetSum - arr[index]);
        int exclude = countSubsequencesWithSum(arr, index + 1, targetSum);
        
        return include + exclude;
    }
    
    public static int countSubsequencesWithSumDP(int[] arr, int targetSum) {
        int n = arr.length;
        int[][] dp = new int[n + 1][targetSum + 1];
        
        for (int i = 0; i <= n; i++) {
            dp[i][0] = 1;
        }
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= targetSum; j++) {
                dp[i][j] = dp[i - 1][j];
                
                if (j >= arr[i - 1]) {
                    dp[i][j] += dp[i - 1][j - arr[i - 1]];
                }
            }
        }
        
        return dp[n][targetSum];
    }
    
    public static int countSubsequencesMemoized(int[] arr, int index, int targetSum, 
                                              int[][] memo) {
        if (targetSum == 0) {
            return 1;
        }
        
        if (index == arr.length || targetSum < 0) {
            return 0;
        }
        
        if (memo[index][targetSum] != -1) {
            return memo[index][targetSum];
        }
        
        int include = countSubsequencesMemoized(arr, index + 1, targetSum - arr[index], memo);
        int exclude = countSubsequencesMemoized(arr, index + 1, targetSum, memo);
        
        memo[index][targetSum] = include + exclude;
        return memo[index][targetSum];
    }
}
```

### 12. Check if There Exists a Subsequence with Sum K
**Problem:** Check if any subsequence exists with given sum.  
**Time Complexity:** O(2^n) worst case, can terminate early  
**Space Complexity:** O(n)

```java
public class SubsequenceExistsWithSumK {
    public static boolean existsSubsequenceWithSum(int[] arr, int index, int targetSum) {
        if (targetSum == 0) {
            return true;
        }
        
        if (index == arr.length || targetSum < 0) {
            return false;
        }
        
        boolean include = existsSubsequenceWithSum(arr, index + 1, targetSum - arr[index]);
        if (include) return true;
        
        boolean exclude = existsSubsequenceWithSum(arr, index + 1, targetSum);
        return exclude;
    }
    
    public static boolean existsSubsequenceWithSumDP(int[] arr, int targetSum) {
        int n = arr.length;
        boolean[][] dp = new boolean[n + 1][targetSum + 1];
        
        for (int i = 0; i <= n; i++) {
            dp[i][0] = true;
        }
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= targetSum; j++) {
                dp[i][j] = dp[i - 1][j];
                
                if (j >= arr[i - 1]) {
                    dp[i][j] = dp[i][j] || dp[i - 1][j - arr[i - 1]];
                }
            }
        }
        
        return dp[n][targetSum];
    }
    
    public static boolean existsSubsequenceOptimized(int[] arr, int targetSum) {
        boolean[] dp = new boolean[targetSum + 1];
        dp[0] = true;
        
        for (int num : arr) {
            for (int j = targetSum; j >= num; j--) {
                dp[j] = dp[j] || dp[j - num];
            }
        }
        
        return dp[targetSum];
    }
    
    public static boolean canPartition(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        
        if (sum % 2 == 1) return false;
        
        return existsSubsequenceOptimized(arr, sum / 2);
    }
}
```

### 13. Generate All Subsets I (Power Set)
**Problem:** Generate all possible subsets of given array.  
**Time Complexity:** O(2^n × n)  
**Space Complexity:** O(2^n × n)

```java
import java.util.*;

public class GenerateSubsets {
    public static List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        generateSubsets(nums, 0, new ArrayList<>(), result);
        return result;
    }
    
    private static void generateSubsets(int[] nums, int index, 
                                       List<Integer> current, 
                                       List<List<Integer>> result) {
        result.add(new ArrayList<>(current));
        
        for (int i = index; i < nums.length; i++) {
            current.add(nums[i]);
            generateSubsets(nums, i + 1, current, result);
            current.remove(current.size() - 1);
        }
    }
    
    public static List<List<Integer>> subsetsBitManipulation(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        int n = nums.length;
        
        for (int mask = 0; mask < (1 << n); mask++) {
            List<Integer> subset = new ArrayList<>();
            
            for (int i = 0; i < n; i++) {
                if ((mask & (1 << i)) != 0) {
                    subset.add(nums[i]);
                }
            }
            
            result.add(subset);
        }
        
        return result;
    }
    
    public static List<List<Integer>> subsetsIterative(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        result.add(new ArrayList<>());
        
        for (int num : nums) {
            int size = result.size();
            for (int i = 0; i < size; i++) {
                List<Integer> newSubset = new ArrayList<>(result.get(i));
                newSubset.add(num);
                result.add(newSubset);
            }
        }
        
        return result;
    }
    
    public static void printAllSubsets(int[] nums) {
        List<List<Integer>> allSubsets = subsets(nums);
        
        System.out.println("All subsets:");
        for (List<Integer> subset : allSubsets) {
            System.out.println(subset);
        }
    }
}
```

### 14. Generate All Subsets II (with duplicates)
**Problem:** Generate all unique subsets when array contains duplicates.  
**Time Complexity:** O(2^n × n)  
**Space Complexity:** O(2^n × n)

```java
import java.util.*;

public class GenerateSubsetsII {
    public static List<List<Integer>> subsetsWithDup(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> result = new ArrayList<>();
        generateSubsetsWithDup(nums, 0, new ArrayList<>(), result);
        return result;
    }
    
    private static void generateSubsetsWithDup(int[] nums, int index, 
                                              List<Integer> current, 
                                              List<List<Integer>> result) {
        result.add(new ArrayList<>(current));
        
        for (int i = index; i < nums.length; i++) {
            if (i > index && nums[i] == nums[i - 1]) {
                continue;
            }
            
            current.add(nums[i]);
            generateSubsetsWithDup(nums, i + 1, current, result);
            current.remove(current.size() - 1);
        }
    }
    
    public static List<List<Integer>> subsetsWithDupSet(int[] nums) {
        Set<List<Integer>> uniqueSubsets = new HashSet<>();
        Arrays.sort(nums);
        generateAllSubsets(nums, 0, new ArrayList<>(), uniqueSubsets);
        return new ArrayList<>(uniqueSubsets);
    }
    
    private static void generateAllSubsets(int[] nums, int index, 
                                          List<Integer> current, 
                                          Set<List<Integer>> uniqueSubsets) {
        if (index == nums.length) {
            uniqueSubsets.add(new ArrayList<>(current));
            return;
        }
        
        current.add(nums[index]);
        generateAllSubsets(nums, index + 1, current, uniqueSubsets);
        
        current.remove(current.size() - 1);
        generateAllSubsets(nums, index + 1, current, uniqueSubsets);
    }
    
    public static List<List<Integer>> subsetsWithDupIterative(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> result = new ArrayList<>();
        result.add(new ArrayList<>());
        
        int start = 0;
        for (int i = 0; i < nums.length; i++) {
            int size = result.size();
            
            if (i > 0 && nums[i] == nums[i - 1]) {
                start = size - start;
            } else {
                start = 0;
            }
            
            for (int j = start; j < size; j++) {
                List<Integer> newSubset = new ArrayList<>(result.get(j));
                newSubset.add(nums[i]);
                result.add(newSubset);
            }
        }
        
        return result;
    }
}
```

### 15. Combination Sum I
**Problem:** Find all combinations that sum to target (can reuse elements).  
**Time Complexity:** O(2^target)  
**Space Complexity:** O(target)

```java
import java.util.*;

public class CombinationSum {
    public static List<List<Integer>> combinationSum(int[] candidates, int target) {
        Arrays.sort(candidates);
        List<List<Integer>> result = new ArrayList<>();
        findCombinations(candidates, 0, target, new ArrayList<>(), result);
        return result;
    }
    
    private static void findCombinations(int[] candidates, int index, int target, 
                                        List<Integer> current, 
                                        List<List<Integer>> result) {
        if (target == 0) {
            result.add(new ArrayList<>(current));
            return;
        }
        
        for (int i = index; i < candidates.length; i++) {
            if (candidates[i] > target) break;
            
            current.add(candidates[i]);
            findCombinations(candidates, i, target - candidates[i], current, result);
            current.remove(current.size() - 1);
        }
    }
    
    public static List<List<Integer>> combinationSumDP(int[] candidates, int target) {
        Arrays.sort(candidates);
        Map<Integer, List<List<Integer>>> dp = new HashMap<>();
        return combinationSumDPHelper(candidates, target, dp);
    }
    
    private static List<List<Integer>> combinationSumDPHelper(int[] candidates, 
                                                             int target, 
                                                             Map<Integer, List<List<Integer>>> dp) {
        if (target == 0) {
            List<List<Integer>> result = new ArrayList<>();
            result.add(new ArrayList<>());
            return result;
        }
        
        if (dp.containsKey(target)) {
            return dp.get(target);
        }
        
        List<List<Integer>> result = new ArrayList<>();
        
        for (int candidate : candidates) {
            if (candidate > target) break;
            
            List<List<Integer>> subResult = combinationSumDPHelper(candidates, 
                                                                  target - candidate, dp);
            
            for (List<Integer> combination : subResult) {
                List<Integer> newCombination = new ArrayList<>();
                newCombination.add(candidate);
                newCombination.addAll(combination);
                Collections.sort(newCombination);
                
                if (!result.contains(newCombination)) {
                    result.add(newCombination);
                }
            }
        }
        
        dp.put(target, result);
        return result;
    }
    
    public static int combinationSumCount(int[] candidates, int target) {
        return combinationSumCountHelper(candidates, 0, target);
    }
    
    private static int combinationSumCountHelper(int[] candidates, int index, int target) {
        if (target == 0) return 1;
        if (target < 0 || index == candidates.length) return 0;
        
        int include = combinationSumCountHelper(candidates, index, target - candidates[index]);
        int exclude = combinationSumCountHelper(candidates, index + 1, target);
        
        return include + exclude;
    }
}
```

### 16. Combination Sum II
**Problem:** Find unique combinations that sum to target (no reuse, duplicates in array).  
**Time Complexity:** O(2^n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class CombinationSum2 {
    public static List<List<Integer>> combinationSum2(int[] candidates, int target) {
        Arrays.sort(candidates);
        List<List<Integer>> result = new ArrayList<>();
        findCombinations(candidates, 0, target, new ArrayList<>(), result);
        return result;
    }
    
    private static void findCombinations(int[] candidates, int index, int target, 
                                        List<Integer> current, 
                                        List<List<Integer>> result) {
        if (target == 0) {
            result.add(new ArrayList<>(current));
            return;
        }
        
        for (int i = index; i < candidates.length; i++) {
            if (i > index && candidates[i] == candidates[i - 1]) continue;
            if (candidates[i] > target) break;
            
            current.add(candidates[i]);
            findCombinations(candidates, i + 1, target - candidates[i], current, result);
            current.remove(current.size() - 1);
        }
    }
    
    public static List<List<Integer>> combinationSum2Set(int[] candidates, int target) {
        Arrays.sort(candidates);
        Set<List<Integer>> uniqueResult = new HashSet<>();
        findCombinationsSet(candidates, 0, target, new ArrayList<>(), uniqueResult);
        return new ArrayList<>(uniqueResult);
    }
    
    private static void findCombinationsSet(int[] candidates, int index, int target, 
                                           List<Integer> current, 
                                           Set<List<Integer>> result) {
        if (target == 0) {
            result.add(new ArrayList<>(current));
            return;
        }
        
        for (int i = index; i < candidates.length; i++) {
            if (candidates[i] > target) break;
            
            current.add(candidates[i]);
            findCombinationsSet(candidates, i + 1, target - candidates[i], current, result);
            current.remove(current.size() - 1);
        }
    }
}
```

### 17. Palindrome Partitioning
**Problem:** Partition string into palindromic substrings.  
**Time Complexity:** O(n × 2^n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class PalindromePartitioning {
    public static List<List<String>> partition(String s) {
        List<List<String>> result = new ArrayList<>();
        partitionHelper(s, 0, new ArrayList<>(), result);
        return result;
    }
    
    private static void partitionHelper(String s, int start, 
                                       List<String> current, 
                                       List<List<String>> result) {
        if (start == s.length()) {
            result.add(new ArrayList<>(current));
            return;
        }
        
        for (int end = start; end < s.length(); end++) {
            if (isPalindrome(s, start, end)) {
                current.add(s.substring(start, end + 1));
                partitionHelper(s, end + 1, current, result);
                current.remove(current.size() - 1);
            }
        }
    }
    
    private static boolean isPalindrome(String s, int start, int end) {
        while (start < end) {
            if (s.charAt(start) != s.charAt(end)) {
                return false;
            }
            start++;
            end--;
        }
        return true;
    }
    
    public static List<List<String>> partitionDP(String s) {
        int n = s.length();
        boolean[][] palindrome = new boolean[n][n];
        
        for (int i = 0; i < n; i++) {
            palindrome[i][i] = true;
        }
        
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                if (len == 2) {
                    palindrome[i][j] = (s.charAt(i) == s.charAt(j));
                } else {
                    palindrome[i][j] = (s.charAt(i) == s.charAt(j)) && palindrome[i + 1][j - 1];
                }
            }
        }
        
        List<List<String>> result = new ArrayList<>();
        partitionDPHelper(s, 0, new ArrayList<>(), result, palindrome);
        return result;
    }
    
    private static void partitionDPHelper(String s, int start, 
                                         List<String> current, 
                                         List<List<String>> result, 
                                         boolean[][] palindrome) {
        if (start == s.length()) {
            result.add(new ArrayList<>(current));
            return;
        }
        
        for (int end = start; end < s.length(); end++) {
            if (palindrome[start][end]) {
                current.add(s.substring(start, end + 1));
                partitionDPHelper(s, end + 1, current, result, palindrome);
                current.remove(current.size() - 1);
            }
        }
    }
}
```

### 18. Word Search
**Problem:** Check if word exists in 2D board using DFS.  
**Time Complexity:** O(m × n × 4^L) where L is word length  
**Space Complexity:** O(L)

```java
public class WordSearch {
    public static boolean exist(char[][] board, String word) {
        int m = board.length;
        int n = board[0].length;
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (dfs(board, word, i, j, 0)) {
                    return true;
                }
            }
        }
        
        return false;
    }
    
    private static boolean dfs(char[][] board, String word, int i, int j, int index) {
        if (index == word.length()) {
            return true;
        }
        
        if (i < 0 || i >= board.length || j < 0 || j >= board[0].length || 
            board[i][j] != word.charAt(index)) {
            return false;
        }
        
        char temp = board[i][j];
        board[i][j] = '#';
        
        boolean found = dfs(board, word, i + 1, j, index + 1) ||
                       dfs(board, word, i - 1, j, index + 1) ||
                       dfs(board, word, i, j + 1, index + 1) ||
                       dfs(board, word, i, j - 1, index + 1);
        
        board[i][j] = temp;
        
        return found;
    }
    
    public static boolean existOptimized(char[][] board, String word) {
        if (board == null || board.length == 0 || word == null || word.length() == 0) {
            return false;
        }
        
        int m = board.length;
        int n = board[0].length;
        boolean[][] visited = new boolean[m][n];
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (board[i][j] == word.charAt(0) && 
                    dfsOptimized(board, word, i, j, 0, visited)) {
                    return true;
                }
            }
        }
        
        return false;
    }
    
    private static boolean dfsOptimized(char[][] board, String word, int i, int j, 
                                       int index, boolean[][] visited) {
        if (index == word.length()) {
            return true;
        }
        
        if (i < 0 || i >= board.length || j < 0 || j >= board[0].length || 
            visited[i][j] || board[i][j] != word.charAt(index)) {
            return false;
        }
        
        visited[i][j] = true;
        
        boolean found = dfsOptimized(board, word, i + 1, j, index + 1, visited) ||
                       dfsOptimized(board, word, i - 1, j, index + 1, visited) ||
                       dfsOptimized(board, word, i, j + 1, index + 1, visited) ||
                       dfsOptimized(board, word, i, j - 1, index + 1, visited);
        
        visited[i][j] = false;
        
        return found;
    }
}
```

### 19. N-Queens Problem
**Problem:** Place N queens on N×N chessboard such that no two queens attack each other.  
**Time Complexity:** O(N!)  
**Space Complexity:** O(N²)

```java
import java.util.*;

public class NQueens {
    public static List<List<String>> solveNQueens(int n) {
        List<List<String>> result = new ArrayList<>();
        char[][] board = new char[n][n];
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                board[i][j] = '.';
            }
        }
        
        solve(board, 0, result);
        return result;
    }
    
    private static void solve(char[][] board, int row, List<List<String>> result) {
        if (row == board.length) {
            result.add(constructSolution(board));
            return;
        }
        
        for (int col = 0; col < board.length; col++) {
            if (isSafe(board, row, col)) {
                board[row][col] = 'Q';
                solve(board, row + 1, result);
                board[row][col] = '.';
            }
        }
    }
    
    private static boolean isSafe(char[][] board, int row, int col) {
        int n = board.length;
        
        for (int i = 0; i < row; i++) {
            if (board[i][col] == 'Q') {
                return false;
            }
        }
        
        for (int i = row - 1, j = col - 1; i >= 0 && j >= 0; i--, j--) {
            if (board[i][j] == 'Q') {
                return false;
            }
        }
        
        for (int i = row - 1, j = col + 1; i >= 0 && j < n; i--, j++) {
            if (board[i][j] == 'Q') {
                return false;
            }
        }
        
        return true;
    }
    
    private static List<String> constructSolution(char[][] board) {
        List<String> solution = new ArrayList<>();
        for (char[] row : board) {
            solution.add(new String(row));
        }
        return solution;
    }
    
    public static List<List<String>> solveNQueensOptimized(int n) {
        List<List<String>> result = new ArrayList<>();
        int[] queens = new int[n];
        solveOptimized(queens, 0, result);
        return result;
    }
    
    private static void solveOptimized(int[] queens, int row, List<List<String>> result) {
        if (row == queens.length) {
            result.add(constructSolutionOptimized(queens));
            return;
        }
        
        for (int col = 0; col < queens.length; col++) {
            queens[row] = col;
            if (isValidPlacement(queens, row)) {
                solveOptimized(queens, row + 1, result);
            }
        }
    }
    
    private static boolean isValidPlacement(int[] queens, int row) {
        for (int i = 0; i < row; i++) {
            if (queens[i] == queens[row] || 
                Math.abs(queens[i] - queens[row]) == Math.abs(i - row)) {
                return false;
            }
        }
        return true;
    }
    
    private static List<String> constructSolutionOptimized(int[] queens) {
        List<String> solution = new ArrayList<>();
        for (int row : queens) {
            StringBuilder sb = new StringBuilder();
            for (int col = 0; col < queens.length; col++) {
                sb.append(col == row ? 'Q' : '.');
            }
            solution.add(sb.toString());
        }
        return solution;
    }
}
```

### 20. Sudoku Solver
**Problem:** Solve 9×9 Sudoku puzzle using backtracking.  
**Time Complexity:** O(9^(n²))  
**Space Complexity:** O(n²)

```java
public class SudokuSolver {
    public static boolean solveSudoku(char[][] board) {
        return solve(board);
    }
    
    private static boolean solve(char[][] board) {
        for (int i = 0; i < 9; i++) {
            for (int j = 0; j < 9; j++) {
                if (board[i][j] == '.') {
                    for (char num = '1'; num <= '9'; num++) {
                        if (isValid(board, i, j, num)) {
                            board[i][j] = num;
                            
                            if (solve(board)) {
                                return true;
                            }
                            
                            board[i][j] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }
    
    private static boolean isValid(char[][] board, int row, int col, char num) {
        for (int i = 0; i < 9; i++) {
            if (board[row][i] == num) {
                return false;
            }
        }
        
        for (int i = 0; i < 9; i++) {
            if (board[i][col] == num) {
                return false;
            }
        }
        
        int startRow = (row / 3) * 3;
        int startCol = (col / 3) * 3;
        
        for (int i = startRow; i < startRow + 3; i++) {
            for (int j = startCol; j < startCol + 3; j++) {
                if (board[i][j] == num) {
                    return false;
                }
            }
        }
        
        return true;
    }
    
    public static boolean solveSudokuOptimized(char[][] board) {
        int[] empty = findEmptyCell(board);
        if (empty == null) {
            return true;
        }
        
        int row = empty[0];
        int col = empty[1];
        
        for (char num = '1'; num <= '9'; num++) {
            if (isValidOptimized(board, row, col, num)) {
                board[row][col] = num;
                
                if (solveSudokuOptimized(board)) {
                    return true;
                }
                
                board[row][col] = '.';
            }
        }
        
        return false;
    }
    
    private static int[] findEmptyCell(char[][] board) {
        for (int i = 0; i < 9; i++) {
            for (int j = 0; j < 9; j++) {
                if (board[i][j] == '.') {
                    return new int[]{i, j};
                }
            }
        }
        return null;
    }
    
    private static boolean isValidOptimized(char[][] board, int row, int col, char num) {
        return !usedInRow(board, row, num) && 
               !usedInCol(board, col, num) && 
               !usedInBox(board, row - row % 3, col - col % 3, num);
    }
    
    private static boolean usedInRow(char[][] board, int row, char num) {
        for (int col = 0; col < 9; col++) {
            if (board[row][col] == num) {
                return true;
            }
        }
        return false;
    }
    
    private static boolean usedInCol(char[][] board, int col, char num) {
        for (int row = 0; row < 9; row++) {
            if (board[row][col] == num) {
                return true;
            }
        }
        return false;
    }
    
    private static boolean usedInBox(char[][] board, int boxStartRow, int boxStartCol, char num) {
        for (int row = 0; row < 3; row++) {
            for (int col = 0; col < 3; col++) {
                if (board[row + boxStartRow][col + boxStartCol] == num) {
                    return true;
                }
            }
        }
        return false;
    }
}
```

### 21. M-Coloring Problem
**Problem:** Color graph with M colors such that no adjacent vertices have same color.  
**Time Complexity:** O(M^V)  
**Space Complexity:** O(V)

```java
import java.util.*;

public class MColoring {
    public static boolean graphColoring(List<List<Integer>> graph, int m, int n) {
        int[] color = new int[n];
        return solve(0, graph, color, n, m);
    }
    
    private static boolean solve(int node, List<List<Integer>> graph, 
                                int[] color, int n, int m) {
        if (node == n) {
            return true;
        }
        
        for (int c = 1; c <= m; c++) {
            if (isSafe(node, graph, color, n, c)) {
                color[node] = c;
                
                if (solve(node + 1, graph, color, n, m)) {
                    return true;
                }
                
                color[node] = 0;
            }
        }
        
        return false;
    }
    
    private static boolean isSafe(int node, List<List<Integer>> graph, 
                                 int[] color, int n, int c) {
        for (int neighbor : graph.get(node)) {
            if (color[neighbor] == c) {
                return false;
            }
        }
        return true;
    }
    
    public static List<int[]> getAllColorings(List<List<Integer>> graph, int m, int n) {
        List<int[]> result = new ArrayList<>();
        int[] color = new int[n];
        findAllColorings(0, graph, color, n, m, result);
        return result;
    }
    
    private static void findAllColorings(int node, List<List<Integer>> graph, 
                                        int[] color, int n, int m, 
                                        List<int[]> result) {
        if (node == n) {
            result.add(color.clone());
            return;
        }
        
        for (int c = 1; c <= m; c++) {
            if (isSafe(node, graph, color, n, c)) {
                color[node] = c;
                findAllColorings(node + 1, graph, color, n, m, result);
                color[node] = 0;
            }
        }
    }
    
    public static boolean graphColoringMatrix(int[][] graph, int m) {
        int n = graph.length;
        int[] color = new int[n];
        return solveMatrix(0, graph, color, n, m);
    }
    
    private static boolean solveMatrix(int node, int[][] graph, 
                                      int[] color, int n, int m) {
        if (node == n) {
            return true;
        }
        
        for (int c = 1; c <= m; c++) {
            if (isSafeMatrix(node, graph, color, n, c)) {
                color[node] = c;
                
                if (solveMatrix(node + 1, graph, color, n, m)) {
                    return true;
                }
                
                color[node] = 0;
            }
        }
        
        return false;
    }
    
    private static boolean isSafeMatrix(int node, int[][] graph, 
                                       int[] color, int n, int c) {
        for (int i = 0; i < n; i++) {
            if (graph[node][i] == 1 && color[i] == c) {
                return false;
            }
        }
        return true;
    }
}
```

### 22. Rat in a Maze
**Problem:** Find all paths for rat to reach destination in maze.  
**Time Complexity:** O(4^(m×n))  
**Space Complexity:** O(m×n)

```java
import java.util.*;

public class RatInMaze {
    public static ArrayList<String> findPath(int[][] m, int n) {
        ArrayList<String> result = new ArrayList<>();
        if (m[0][0] == 0 || m[n - 1][n - 1] == 0) {
            return result;
        }
        
        boolean[][] visited = new boolean[n][n];
        solve(m, 0, 0, n, "", result, visited);
        return result;
    }
    
    private static void solve(int[][] m, int i, int j, int n, String path, 
                             ArrayList<String> result, boolean[][] visited) {
        if (i == n - 1 && j == n - 1) {
            result.add(path);
            return;
        }
        
        if (i < 0 || i >= n || j < 0 || j >= n || visited[i][j] || m[i][j] == 0) {
            return;
        }
        
        visited[i][j] = true;
        
        solve(m, i + 1, j, n, path + "D", result, visited);
        solve(m, i, j - 1, n, path + "L", result, visited);
        solve(m, i, j + 1, n, path + "R", result, visited);
        solve(m, i - 1, j, n, path + "U", result, visited);
        
        visited[i][j] = false;
    }
    
    public static ArrayList<String> findPathOptimized(int[][] m, int n) {
        ArrayList<String> result = new ArrayList<>();
        if (m[0][0] == 0 || m[n - 1][n - 1] == 0) {
            return result;
        }
        
        int[] di = {1, 0, 0, -1};
        int[] dj = {0, -1, 1, 0};
        String[] direction = {"D", "L", "R", "U"};
        boolean[][] visited = new boolean[n][n];
        
        solveOptimized(m, 0, 0, n, "", result, visited, di, dj, direction);
        return result;
    }
    
    private static void solveOptimized(int[][] m, int i, int j, int n, String path, 
                                      ArrayList<String> result, boolean[][] visited,
                                      int[] di, int[] dj, String[] direction) {
        if (i == n - 1 && j == n - 1) {
            result.add(path);
            return;
        }
        
        visited[i][j] = true;
        
        for (int ind = 0; ind < 4; ind++) {
            int nexti = i + di[ind];
            int nextj = j + dj[ind];
            
            if (nexti >= 0 && nextj >= 0 && nexti < n && nextj < n && 
                !visited[nexti][nextj] && m[nexti][nextj] == 1) {
                
                solveOptimized(m, nexti, nextj, n, path + direction[ind], 
                              result, visited, di, dj, direction);
            }
        }
        
        visited[i][j] = false;
    }
    
    public static boolean hasPath(int[][] m, int n) {
        if (m[0][0] == 0 || m[n - 1][n - 1] == 0) {
            return false;
        }
        
        boolean[][] visited = new boolean[n][n];
        return canReachDestination(m, 0, 0, n, visited);
    }
    
    private static boolean canReachDestination(int[][] m, int i, int j, int n, 
                                              boolean[][] visited) {
        if (i == n - 1 && j == n - 1) {
            return true;
        }
        
        if (i < 0 || i >= n || j < 0 || j >= n || visited[i][j] || m[i][j] == 0) {
            return false;
        }
        
        visited[i][j] = true;
        
        boolean found = canReachDestination(m, i + 1, j, n, visited) ||
                       canReachDestination(m, i, j - 1, n, visited) ||
                       canReachDestination(m, i, j + 1, n, visited) ||
                       canReachDestination(m, i - 1, j, n, visited);
        
        visited[i][j] = false;
        
        return found;
    }
}
```

### 23. Word Break II
**Problem:** Break string into dictionary words, return all possible sentences.  
**Time Complexity:** O(2^n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class WordBreak2 {
    public static List<String> wordBreak(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>(wordDict);
        Map<String, List<String>> memo = new HashMap<>();
        return helper(s, wordSet, memo);
    }
    
    private static List<String> helper(String s, Set<String> wordSet, 
                                      Map<String, List<String>> memo) {
        if (memo.containsKey(s)) {
            return memo.get(s);
        }
        
        List<String> result = new ArrayList<>();
        
        if (s.length() == 0) {
            result.add("");
            return result;
        }
        
        for (int i = 1; i <= s.length(); i++) {
            String prefix = s.substring(0, i);
            
            if (wordSet.contains(prefix)) {
                List<String> suffixBreaks = helper(s.substring(i), wordSet, memo);
                
                for (String suffix : suffixBreaks) {
                    if (suffix.length() == 0) {
                        result.add(prefix);
                    } else {
                        result.add(prefix + " " + suffix);
                    }
                }
            }
        }
        
        memo.put(s, result);
        return result;
    }
    
    public static List<String> wordBreakBacktrack(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>(wordDict);
        List<String> result = new ArrayList<>();
        backtrack(s, 0, wordSet, new StringBuilder(), result);
        return result;
    }
    
    private static void backtrack(String s, int start, Set<String> wordSet, 
                                 StringBuilder current, List<String> result) {
        if (start == s.length()) {
            result.add(current.toString().trim());
            return;
        }
        
        for (int end = start + 1; end <= s.length(); end++) {
            String word = s.substring(start, end);
            
            if (wordSet.contains(word)) {
                int len = current.length();
                if (len > 0) current.append(" ");
                current.append(word);
                
                backtrack(s, end, wordSet, current, result);
                
                current.setLength(len);
            }
        }
    }
    
    public static List<String> wordBreakDP(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>(wordDict);
        List<List<String>> dp = new ArrayList<>();
        
        for (int i = 0; i <= s.length(); i++) {
            dp.add(new ArrayList<>());
        }
        
        dp.get(0).add("");
        
        for (int i = 1; i <= s.length(); i++) {
            for (int j = 0; j < i; j++) {
                String word = s.substring(j, i);
                
                if (wordSet.contains(word) && !dp.get(j).isEmpty()) {
                    for (String sentence : dp.get(j)) {
                        if (sentence.isEmpty()) {
                            dp.get(i).add(word);
                        } else {
                            dp.get(i).add(sentence + " " + word);
                        }
                    }
                }
            }
        }
        
        return dp.get(s.length());
    }
}
```

### 24. Expression Add Operators
**Problem:** Add +, -, * operators to make expression equal target.  
**Time Complexity:** O(4^n)  
**Space Complexity:** O(n)

```java
import java.util.*;

public class ExpressionAddOperators {
    public static List<String> addOperators(String num, int target) {
        List<String> result = new ArrayList<>();
        if (num == null || num.length() == 0) return result;
        
        backtrack(num, target, 0, "", 0, 0, result);
        return result;
    }
    
    private static void backtrack(String num, int target, int index, String path, 
                                 long eval, long prev, List<String> result) {
        if (index == num.length()) {
            if (eval == target) {
                result.add(path);
            }
            return;
        }
        
        for (int i = index; i < num.length(); i++) {
            String curr = num.substring(index, i + 1);
            
            if (curr.length() > 1 && curr.charAt(0) == '0') {
                break;
            }
            
            long currVal = Long.parseLong(curr);
            
            if (index == 0) {
                backtrack(num, target, i + 1, curr, currVal, currVal, result);
            } else {
                backtrack(num, target, i + 1, path + "+" + curr, eval + currVal, currVal, result);
                
                backtrack(num, target, i + 1, path + "-" + curr, eval - currVal, -currVal, result);
                
                backtrack(num, target, i + 1, path + "*" + curr, 
                         eval - prev + prev * currVal, prev * currVal, result);
            }
        }
    }
    
    public static List<String> addOperatorsOptimized(String num, int target) {
        List<String> result = new ArrayList<>();
        if (num == null || num.length() == 0) return result;
        
        char[] path = new char[num.length() * 2 - 1];
        long[] values = new long[num.length()];
        char[] ops = new char[num.length()];
        
        backtrackOptimized(num, target, 0, 0, path, 0, values, ops, 0, result);
        return result;
    }
    
    private static void backtrackOptimized(String num, int target, int index, int pathLen,
                                          char[] path, long eval, long[] values, 
                                          char[] ops, int level, List<String> result) {
        if (index == num.length()) {
            if (eval == target) {
                result.add(new String(path, 0, pathLen));
            }
            return;
        }
        
        long n = 0;
        int j = pathLen;
        
        if (index > 0) {
            pathLen++;
        }
        
        for (int i = index; i < num.length(); i++) {
            if (i > index && num.charAt(index) == '0') {
                break;
            }
            
            n = n * 10 + (num.charAt(i) - '0');
            path[pathLen++] = num.charAt(i);
            
            if (index == 0) {
                backtrackOptimized(num, target, i + 1, pathLen, path, n, values, ops, level, result);
            } else {
                path[j] = '+';
                values[level] = n;
                ops[level] = '+';
                backtrackOptimized(num, target, i + 1, pathLen, path, eval + n, values, ops, level + 1, result);
                
                path[j] = '-';
                values[level] = n;
                ops[level] = '-';
                backtrackOptimized(num, target, i + 1, pathLen, path, eval - n, values, ops, level + 1, result);
                
                path[j] = '*';
                values[level] = n;
                ops[level] = '*';
                if (level > 0) {
                    long prev = values[level - 1];
                    char prevOp = ops[level - 1];
                    if (prevOp == '+') {
                        backtrackOptimized(num, target, i + 1, pathLen, path, eval - prev + prev * n, values, ops, level + 1, result);
                    } else {
                        backtrackOptimized(num, target, i + 1, pathLen, path, eval + prev - prev * n, values, ops, level + 1, result);
                    }
                }
            }
        }
    }
}
```

### 25. Generate Parentheses
**Problem:** Generate all valid parentheses combinations for n pairs.  
**Time Complexity:** O(4^n / √n) - Catalan number  
**Space Complexity:** O(n)

```java
import java.util.*;

public class GenerateParentheses {
    public static List<String> generateParenthesis(int n) {
        List<String> result = new ArrayList<>();
        backtrack(result, "", 0, 0, n);
        return result;
    }
    
    private static void backtrack(List<String> result, String current, 
                                 int open, int close, int max) {
        if (current.length() == max * 2) {
            result.add(current);
            return;
        }
        
        if (open < max) {
            backtrack(result, current + "(", open + 1, close, max);
        }
        
        if (close < open) {
            backtrack(result, current + ")", open, close + 1, max);
        }
    }
    
    public static List<String> generateParenthesisDP(int n) {
        List<List<String>> dp = new ArrayList<>();
        
        for (int i = 0; i <= n; i++) {
            dp.add(new ArrayList<>());
        }
        
        dp.get(0).add("");
        
        for (int i = 1; i <= n; i++) {
            for (int j = 0; j < i; j++) {
                for (String left : dp.get(j)) {
                    for (String right : dp.get(i - 1 - j)) {
                        dp.get(i).add("(" + left + ")" + right);
                    }
                }
            }
        }
        
        return dp.get(n);
    }
    
    public static List<String> generateParenthesisIterative(int n) {
        List<String> result = new ArrayList<>();
        if (n == 0) return result;
        
        Stack<Node> stack = new Stack<>();
        stack.push(new Node("", 0, 0));
        
        while (!stack.isEmpty()) {
            Node node = stack.pop();
            
            if (node.str.length() == 2 * n) {
                result.add(node.str);
                continue;
            }
            
            if (node.open < n) {
                stack.push(new Node(node.str + "(", node.open + 1, node.close));
            }
            
            if (node.close < node.open) {
                stack.push(new Node(node.str + ")", node.open, node.close + 1));
            }
        }
        
        return result;
    }
    
    static class Node {
        String str;
        int open;
        int close;
        
        Node(String str, int open, int close) {
            this.str = str;
            this.open = open;
            this.close = close;
        }
    }
    
    public static boolean isValidParentheses(String s) {
        int count = 0;
        
        for (char c : s.toCharArray()) {
            if (c == '(') {
                count++;
            } else if (c == ')') {
                count--;
                if (count < 0) return false;
            }
        }
        
        return count == 0;
    }
}
```

---

## Bit Manipulation

### Binary Number System
- **Bit**: Basic unit (0 or 1)
- **Byte**: 8 bits
- **Word**: 32 bits (int) or 64 bits (long)

### Bitwise Operators
```java
public class BitwiseOperators {
    public static void demonstrateOperators(int a, int b) {
        System.out.println("a = " + a + " (" + Integer.toBinaryString(a) + ")");
        System.out.println("b = " + b + " (" + Integer.toBinaryString(b) + ")");
        
        System.out.println("a & b = " + (a & b) + " (AND)");
        System.out.println("a | b = " + (a | b) + " (OR)");
        System.out.println("a ^ b = " + (a ^ b) + " (XOR)");
        System.out.println("~a = " + (~a) + " (NOT)");
        System.out.println("a << 1 = " + (a << 1) + " (Left Shift)");
        System.out.println("a >> 1 = " + (a >> 1) + " (Right Shift)");
        System.out.println("a >>> 1 = " + (a >>> 1) + " (Unsigned Right Shift)");
    }
}
```

### XOR Properties
```java
public class XORProperties {
    public static void demonstrateXORProperties() {
        int a = 5;
        
        System.out.println("a ^ 0 = " + (a ^ 0)); // a ^ 0 = a
        System.out.println("a ^ a = " + (a ^ a)); // a ^ a = 0
        System.out.println("a ^ b ^ b = " + (a ^ 3 ^ 3)); // a ^ b ^ b = a
        
        // XOR is commutative and associative
        int b = 3, c = 7;
        System.out.println("(a ^ b) ^ c = " + ((a ^ b) ^ c));
        System.out.println("a ^ (b ^ c) = " + (a ^ (b ^ c)));
    }
}
```

### 1. Introduction to Bit Manipulation
**Concept:** Understanding binary representation and basic operations.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class BitManipulationIntro {
    public static void printBinary(int n) {
        System.out.println("Binary of " + n + ": " + Integer.toBinaryString(n));
    }
    
    public static void printBinary32Bit(int n) {
        for (int i = 31; i >= 0; i--) {
            int bit = (n >> i) & 1;
            System.out.print(bit);
            if (i % 4 == 0) System.out.print(" ");
        }
        System.out.println();
    }
    
    public static int convertBinaryToDecimal(String binary) {
        return Integer.parseInt(binary, 2);
    }
    
    public static String convertDecimalToBinary(int decimal) {
        return Integer.toBinaryString(decimal);
    }
    
    public static void demonstrateBasicOperations() {
        int a = 5;  // 101
        int b = 3;  // 011
        
        System.out.println("AND: " + (a & b));  // 001 = 1
        System.out.println("OR: " + (a | b));   // 111 = 7
        System.out.println("XOR: " + (a ^ b));  // 110 = 6
        System.out.println("NOT a: " + (~a));   // ...11111010 = -6
    }
}
```

### 2. Check if i-th Bit is Set or Not
**Problem:** Check if the i-th bit (0-indexed from right) is set.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class CheckIthBit {
    public static boolean isIthBitSet(int n, int i) {
        return (n & (1 << i)) != 0;
    }
    
    public static boolean isIthBitSetMethod2(int n, int i) {
        return ((n >> i) & 1) == 1;
    }
    
    public static boolean isIthBitSetDivision(int n, int i) {
        return ((n / (1 << i)) % 2) == 1;
    }
    
    public static void printAllSetBits(int n) {
        System.out.print("Set bits in " + n + ": ");
        for (int i = 0; i < 32; i++) {
            if (isIthBitSet(n, i)) {
                System.out.print(i + " ");
            }
        }
        System.out.println();
    }
    
    public static int getIthBit(int n, int i) {
        return (n >> i) & 1;
    }
}
```

### 3. Odd or Even Using Bit Manipulation
**Problem:** Check if number is odd or even using bits.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class OddEven {
    public static boolean isOdd(int n) {
        return (n & 1) == 1;
    }
    
    public static boolean isEven(int n) {
        return (n & 1) == 0;
    }
    
    public static String checkOddEven(int n) {
        return (n & 1) == 1 ? "Odd" : "Even";
    }
    
    public static void separateOddEven(int[] arr) {
        System.out.print("Odd numbers: ");
        for (int num : arr) {
            if (isOdd(num)) {
                System.out.print(num + " ");
            }
        }
        System.out.println();
        
        System.out.print("Even numbers: ");
        for (int num : arr) {
            if (isEven(num)) {
                System.out.print(num + " ");
            }
        }
        System.out.println();
    }
}
```

### 4. Check if Number is Power of 2
**Problem:** Check if given number is power of 2.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class PowerOfTwo {
    public static boolean isPowerOfTwo(int n) {
        return n > 0 && (n & (n - 1)) == 0;
    }
    
    public static boolean isPowerOfTwoMethod2(int n) {
        if (n <= 0) return false;
        
        int count = 0;
        while (n > 0) {
            if ((n & 1) == 1) {
                count++;
            }
            n >>= 1;
        }
        
        return count == 1;
    }
    
    public static boolean isPowerOfTwoLogMethod(int n) {
        if (n <= 0) return false;
        
        return (Math.ceil(Math.log(n) / Math.log(2)) == 
                Math.floor(Math.log(n) / Math.log(2)));
    }
    
    public static int nextPowerOfTwo(int n) {
        if (n <= 0) return 1;
        if (isPowerOfTwo(n)) return n;
        
        int power = 1;
        while (power < n) {
            power <<= 1;
        }
        return power;
    }
    
    public static int previousPowerOfTwo(int n) {
        if (n <= 1) return 1;
        
        int power = 1;
        while ((power << 1) < n) {
            power <<= 1;
        }
        return power;
    }
}
```

### 5. Count the Number of Set Bits
**Problem:** Count number of 1s in binary representation.  
**Time Complexity:** O(log n) or O(1) for fixed-size integers  
**Space Complexity:** O(1)

```java
public class CountSetBits {
    public static int countSetBits(int n) {
        int count = 0;
        while (n > 0) {
            count++;
            n &= (n - 1);  // Remove rightmost set bit
        }
        return count;
    }
    
    public static int countSetBitsSimple(int n) {
        int count = 0;
        while (n > 0) {
            if ((n & 1) == 1) {
                count++;
            }
            n >>= 1;
        }
        return count;
    }
    
    public static int countSetBitsBuiltIn(int n) {
        return Integer.bitCount(n);
    }
    
    public static int countSetBitsLookupTable(int n) {
        int[] table = new int[256];
        
        // Precompute for all 8-bit numbers
        for (int i = 0; i < 256; i++) {
            table[i] = (i & 1) + table[i / 2];
        }
        
        int count = 0;
        count += table[n & 0xff];
        n >>= 8;
        count += table[n & 0xff];
        n >>= 8;
        count += table[n & 0xff];
        n >>= 8;
        count += table[n & 0xff];
        
        return count;
    }
    
    public static long countSetBitsRange(int n) {
        if (n <= 0) return 0;
        
        long count = 0;
        for (int i = 1; i <= n; i++) {
            count += countSetBits(i);
        }
        return count;
    }
    
    public static int countSetBitsBrianKernighan(int n) {
        int count = 0;
        while (n != 0) {
            n &= (n - 1);  // Clear the lowest set bit
            count++;
        }
        return count;
    }
}
```

### 6. Set the i-th Bit
**Problem:** Set the i-th bit to 1.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class SetIthBit {
    public static int setIthBit(int n, int i) {
        return n | (1 << i);
    }
    
    public static int setBit(int n, int position) {
        return n | (1 << position);
    }
    
    public static int setMultipleBits(int n, int[] positions) {
        for (int pos : positions) {
            n = setIthBit(n, pos);
        }
        return n;
    }
    
    public static int setRangeOfBits(int n, int left, int right) {
        // Set bits from position right to left (inclusive)
        for (int i = right; i <= left; i++) {
            n = setIthBit(n, i);
        }
        return n;
    }
    
    public static int setAllBits(int n, int totalBits) {
        return (1 << totalBits) - 1;  // All bits set for totalBits
    }
}
```

### 7. Clear the i-th Bit
**Problem:** Clear the i-th bit (set to 0).  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class ClearIthBit {
    public static int clearIthBit(int n, int i) {
        return n & ~(1 << i);
    }
    
    public static int clearBit(int n, int position) {
        return n & ~(1 << position);
    }
    
    public static int clearMultipleBits(int n, int[] positions) {
        for (int pos : positions) {
            n = clearIthBit(n, pos);
        }
        return n;
    }
    
    public static int clearRangeOfBits(int n, int left, int right) {
        // Clear bits from position right to left (inclusive)
        for (int i = right; i <= left; i++) {
            n = clearIthBit(n, i);
        }
        return n;
    }
    
    public static int clearAllBitsExceptLSB(int n) {
        return n & 1;
    }
    
    public static int clearAllBitsFromMSBToI(int n, int i) {
        // Clear all bits from MSB down to position i (inclusive)
        int mask = (1 << i) - 1;
        return n & mask;
    }
    
    public static int clearAllBitsFromITo0(int n, int i) {
        // Clear all bits from position i to 0 (inclusive)
        int mask = ~((1 << (i + 1)) - 1);
        return n & mask;
    }
}
```

### 8. Toggle the i-th Bit
**Problem:** Toggle the i-th bit (0→1, 1→0).  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class ToggleIthBit {
    public static int toggleIthBit(int n, int i) {
        return n ^ (1 << i);
    }
    
    public static int toggleBit(int n, int position) {
        return n ^ (1 << position);
    }
    
    public static int toggleMultipleBits(int n, int[] positions) {
        for (int pos : positions) {
            n = toggleIthBit(n, pos);
        }
        return n;
    }
    
    public static int toggleRangeOfBits(int n, int left, int right) {
        // Toggle bits from position right to left (inclusive)
        for (int i = right; i <= left; i++) {
            n = toggleIthBit(n, i);
        }
        return n;
    }
    
    public static int toggleAllBits(int n) {
        return ~n;
    }
    
    public static int toggleRightmostSetBit(int n) {
        return n & (n - 1);
    }
    
    public static int toggleRightmostUnsetBit(int n) {
        return n | (n + 1);
    }
}
```

### 9. Remove the Last Set Bit (Rightmost)
**Problem:** Remove the rightmost set bit from number.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class RemoveLastSetBit {
    public static int removeLastSetBit(int n) {
        return n & (n - 1);
    }
    
    public static int removeRightmostSetBit(int n) {
        return n & (n - 1);
    }
    
    public static int isolateRightmostSetBit(int n) {
        return n & (-n);
    }
    
    public static int removeAllSetBitsFromRight(int n) {
        while (n > 0) {
            n &= (n - 1);
        }
        return n;
    }
    
    public static int removeKRightmostSetBits(int n, int k) {
        for (int i = 0; i < k && n > 0; i++) {
            n &= (n - 1);
        }
        return n;
    }
    
    public static boolean hasOnlyOneSetBit(int n) {
        return n > 0 && (n & (n - 1)) == 0;
    }
    
    public static int positionOfRightmostSetBit(int n) {
        if (n == 0) return -1;
        
        int position = 0;
        while ((n & 1) == 0) {
            n >>= 1;
            position++;
        }
        return position;
    }
}
```

### 10. Check if a Number is Power of 2 or Not
**Problem:** Advanced power of 2 checking with multiple methods.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class AdvancedPowerOfTwo {
    public static boolean isPowerOfTwo(int n) {
        return n > 0 && (n & (n - 1)) == 0;
    }
    
    public static boolean isPowerOfTwoFloat(float n) {
        return n > 0 && (n == (int)n) && isPowerOfTwo((int)n);
    }
    
    public static boolean isPowerOfTwoString(String s) {
        try {
            int n = Integer.parseInt(s);
            return isPowerOfTwo(n);
        } catch (NumberFormatException e) {
            return false;
        }
    }
    
    public static int nearestPowerOfTwo(int n) {
        if (n <= 1) return 1;
        
        int lower = previousPowerOfTwo(n);
        int upper = nextPowerOfTwo(n);
        
        return (n - lower) <= (upper - n) ? lower : upper;
    }
    
    private static int previousPowerOfTwo(int n) {
        int power = 1;
        while ((power << 1) <= n) {
            power <<= 1;
        }
        return power;
    }
    
    private static int nextPowerOfTwo(int n) {
        if (isPowerOfTwo(n)) return n;
        
        int power = 1;
        while (power < n) {
            power <<= 1;
        }
        return power;
    }
    
    public static boolean isPowerOfTwoRecursive(int n) {
        if (n <= 0) return false;
        if (n == 1) return true;
        if (n % 2 != 0) return false;
        
        return isPowerOfTwoRecursive(n / 2);
    }
}
```

### 11. Count Number of Set Bits (Advanced)
**Problem:** Efficient counting with various optimization techniques.  
**Time Complexity:** O(1) for lookup table, O(log n) for others  
**Space Complexity:** O(1) or O(256) for lookup table

```java
public class AdvancedCountSetBits {
    public static int countSetBits(int n) {
        return Integer.bitCount(n);
    }
    
    public static int countSetBitsBrianKernighan(int n) {
        int count = 0;
        while (n != 0) {
            n &= (n - 1);
            count++;
        }
        return count;
    }
    
    public static int countSetBitsLookupTable(int n) {
        int[] BitsSetTable256 = new int[256];
        
        BitsSetTable256[0] = 0;
        for (int i = 1; i < 256; i++) {
            BitsSetTable256[i] = (i & 1) + BitsSetTable256[i / 2];
        }
        
        int count = 0;
        count += BitsSetTable256[n & 0xff];
        n >>= 8;
        count += BitsSetTable256[n & 0xff];
        n >>= 8;
        count += BitsSetTable256[n & 0xff];
        n >>= 8;
        count += BitsSetTable256[n & 0xff];
        
        return count;
    }
    
    public static long countSetBitsInRange(int n) {
        long totalCount = 0;
        for (int i = 1; i <= n; i++) {
            totalCount += countSetBits(i);
        }
        return totalCount;
    }
    
    public static long countSetBitsInRangeEfficient(int n) {
        if (n <= 0) return 0;
        
        return countSetBitsUtil(n);
    }
    
    private static long countSetBitsUtil(int n) {
        if (n <= 1) return n;
        
        int powerOf2 = 0;
        while ((1 << (powerOf2 + 1)) <= n) {
            powerOf2++;
        }
        
        return (1L << (powerOf2 - 1)) * powerOf2 + 
               (n - (1 << powerOf2) + 1) + 
               countSetBitsUtil(n - (1 << powerOf2));
    }
    
    public static int countSetBitsInArray(int[] arr) {
        int totalCount = 0;
        for (int num : arr) {
            totalCount += countSetBits(num);
        }
        return totalCount;
    }
}
```

### 12. Swap Two Numbers
**Problem:** Swap two numbers using XOR without extra variable.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class SwapNumbers {
    public static void swapUsingXOR(int a, int b) {
        System.out.println("Before swap: a = " + a + ", b = " + b);
        
        if (a != b) {  // Avoid swapping same numbers
            a = a ^ b;
            b = a ^ b;  // b = (a ^ b) ^ b = a
            a = a ^ b;  // a = (a ^ b) ^ a = b
        }
        
        System.out.println("After swap: a = " + a + ", b = " + b);
    }
    
    public static int[] swapArray(int[] arr, int i, int j) {
        if (i != j && i >= 0 && j >= 0 && i < arr.length && j < arr.length) {
            arr[i] = arr[i] ^ arr[j];
            arr[j] = arr[i] ^ arr[j];
            arr[i] = arr[i] ^ arr[j];
        }
        return arr;
    }
    
    public static void swapUsingAddition(int a, int b) {
        System.out.println("Before swap: a = " + a + ", b = " + b);
        
        a = a + b;
        b = a - b;  // b = (a + b) - b = a
        a = a - b;  // a = (a + b) - a = b
        
        System.out.println("After swap: a = " + a + ", b = " + b);
    }
    
    public static void swapUsingMultiplication(int a, int b) {
        if (a != 0 && b != 0) {
            System.out.println("Before swap: a = " + a + ", b = " + b);
            
            a = a * b;
            b = a / b;  // b = (a * b) / b = a
            a = a / b;  // a = (a * b) / a = b
            
            System.out.println("After swap: a = " + a + ", b = " + b);
        }
    }
    
    public static void swapBits(int n, int i, int j) {
        if (((n >> i) & 1) != ((n >> j) & 1)) {
            n ^= (1 << i) | (1 << j);
        }
        System.out.println("Number after swapping bits at positions " + i + " and " + j + ": " + n);
    }
}
```

### 13. Divide Two Integers Without Using Multiplication, Division and Mod Operator
**Problem:** Implement division using bit manipulation.  
**Time Complexity:** O(log n)  
**Space Complexity:** O(1)

```java
public class DivideIntegers {
    public static int divide(int dividend, int divisor) {
        if (divisor == 0) {
            throw new ArithmeticException("Division by zero");
        }
        
        if (dividend == Integer.MIN_VALUE && divisor == -1) {
            return Integer.MAX_VALUE;
        }
        
        boolean negative = (dividend < 0) ^ (divisor < 0);
        
        long absDividend = Math.abs((long) dividend);
        long absDivisor = Math.abs((long) divisor);
        
        long result = 0;
        
        while (absDividend >= absDivisor) {
            long temp = absDivisor;
            long multiple = 1;
            
            while (absDividend >= (temp << 1)) {
                temp <<= 1;
                multiple <<= 1;
            }
            
            absDividend -= temp;
            result += multiple;
        }
        
        if (negative) {
            result = -result;
        }
        
        return (int) Math.max(Integer.MIN_VALUE, Math.min(Integer.MAX_VALUE, result));
    }
    
    public static int divideRecursive(int dividend, int divisor) {
        if (divisor == 0) return Integer.MAX_VALUE;
        if (dividend == 0) return 0;
        
        boolean isNegative = (dividend < 0) ^ (divisor < 0);
        
        long absDividend = Math.abs((long) dividend);
        long absDivisor = Math.abs((long) divisor);
        
        long result = divideHelper(absDividend, absDivisor);
        
        if (isNegative) {
            result = -result;
        }
        
        if (result > Integer.MAX_VALUE) return Integer.MAX_VALUE;
        if (result < Integer.MIN_VALUE) return Integer.MIN_VALUE;
        
        return (int) result;
    }
    
    private static long divideHelper(long dividend, long divisor) {
        if (dividend < divisor) return 0;
        
        long sum = divisor;
        long multiple = 1;
        
        while ((sum + sum) <= dividend) {
            sum += sum;
            multiple += multiple;
        }
        
        return multiple + divideHelper(dividend - sum, divisor);
    }
    
    public static int divideUsingSubtraction(int dividend, int divisor) {
        if (divisor == 0) return Integer.MAX_VALUE;
        
        boolean isNegative = (dividend < 0) ^ (divisor < 0);
        
        dividend = Math.abs(dividend);
        divisor = Math.abs(divisor);
        
        int quotient = 0;
        while (dividend >= divisor) {
            dividend -= divisor;
            quotient++;
        }
        
        return isNegative ? -quotient : quotient;
    }
}
```

### Find the Two Non-Repeating Elements
**Problem:** In array where every element appears twice except two, find those two.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class TwoNonRepeatingElements {
    public static int[] findTwoNonRepeating(int[] arr) {
        int xor = 0;
        
        // XOR all elements
        for (int num : arr) {
            xor ^= num;
        }
        
        // Find rightmost set bit
        int rightmostSetBit = xor & (-xor);
        
        int num1 = 0, num2 = 0;
        
        // Divide elements into two groups
        for (int num : arr) {
            if ((num & rightmostSetBit) != 0) {
                num1 ^= num;
            } else {
                num2 ^= num;
            }
        }
        
        return new int[]{num1, num2};
    }
    
    public static int[] findTwoNonRepeatingSet(int[] arr) {
        Set<Integer> set = new HashSet<>();
        
        for (int num : arr) {
            if (set.contains(num)) {
                set.remove(num);
            } else {
                set.add(num);
            }
        }
        
        return set.stream().mapToInt(Integer::intValue).toArray();
    }
    
    public static void printTwoNonRepeating(int[] arr) {
        int[] result = findTwoNonRepeating(arr);
        System.out.println("Two non-repeating elements: " + result[0] + " and " + result[1]);
    }
}
```

### Power Set Using Bit Manipulation
**Problem:** Generate all subsets using bit manipulation.  
**Time Complexity:** O(n × 2^n)  
**Space Complexity:** O(2^n)

```java
import java.util.*;

public class PowerSet {
    public static List<List<Integer>> powerSet(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        int n = nums.length;
        
        // Generate all 2^n subsets
        for (int mask = 0; mask < (1 << n); mask++) {
            List<Integer> subset = new ArrayList<>();
            
            for (int i = 0; i < n; i++) {
                // Check if i-th bit is set
                if ((mask & (1 << i)) != 0) {
                    subset.add(nums[i]);
                }
            }
            
            result.add(subset);
        }
        
        return result;
    }
    
    public static void printPowerSet(int[] nums) {
        List<List<Integer>> powerSet = powerSet(nums);
        
        System.out.println("Power set:");
        for (List<Integer> subset : powerSet) {
            System.out.println(subset);
        }
    }
    
    public static List<String> powerSetStrings(String s) {
        List<String> result = new ArrayList<>();
        int n = s.length();
        
        for (int mask = 0; mask < (1 << n); mask++) {
            StringBuilder subset = new StringBuilder();
            
            for (int i = 0; i < n; i++) {
                if ((mask & (1 << i)) != 0) {
                    subset.append(s.charAt(i));
                }
            }
            
            result.add(subset.toString());
        }
        
        return result;
    }
    
    public static int countSubsets(int[] nums, int target) {
        int n = nums.length;
        int count = 0;
        
        for (int mask = 0; mask < (1 << n); mask++) {
            int sum = 0;
            
            for (int i = 0; i < n; i++) {
                if ((mask & (1 << i)) != 0) {
                    sum += nums[i];
                }
            }
            
            if (sum == target) {
                count++;
            }
        }
        
        return count;
    }
}
```

### XOR of Numbers in Given Range
**Problem:** Find XOR of all numbers from L to R efficiently.  
**Time Complexity:** O(1)  
**Space Complexity:** O(1)

```java
public class XORRange {
    public static int xorFromOneToN(int n) {
        switch (n % 4) {
            case 0: return n;
            case 1: return 1;
            case 2: return n + 1;
            case 3: return 0;
            default: return 0;
        }
    }
    
    public static int xorInRange(int l, int r) {
        return xorFromOneToN(r) ^ xorFromOneToN(l - 1);
    }
    
    public static int xorInRangeBruteForce(int l, int r) {
        int xor = 0;
        for (int i = l; i <= r; i++) {
            xor ^= i;
        }
        return xor;
    }
    
    public static void demonstrateXORProperties() {
        System.out.println("XOR from 1 to 1: " + xorFromOneToN(1));
        System.out.println("XOR from 1 to 2: " + xorFromOneToN(2));
        System.out.println("XOR from 1 to 3: " + xorFromOneToN(3));
        System.out.println("XOR from 1 to 4: " + xorFromOneToN(4));
        System.out.println("XOR from 1 to 5: " + xorFromOneToN(5));
        System.out.println("XOR from 1 to 6: " + xorFromOneToN(6));
        System.out.println("XOR from 1 to 7: " + xorFromOneToN(7));
        System.out.println("XOR from 1 to 8: " + xorFromOneToN(8));
    }
    
    public static int xorFromZeroToN(int n) {
        if (n % 4 == 0) return n;
        if (n % 4 == 1) return 1;
        if (n % 4 == 2) return n + 1;
        return 0;
    }
}
```

### Single Number Variations
**Problem:** Various single number problems using XOR properties.  
**Time Complexity:** O(n)  
**Space Complexity:** O(1)

```java
import java.util.*;

public class SingleNumberProblems {
    // Every element appears twice except one
    public static int singleNumber(int[] nums) {
        int result = 0;
        for (int num : nums) {
            result ^= num;
        }
        return result;
    }
    
    // Every element appears three times except one
    public static int singleNumberII(int[] nums) {
        int ones = 0, twos = 0;
        
        for (int num : nums) {
            ones = (ones ^ num) & ~twos;
            twos = (twos ^ num) & ~ones;
        }
        
        return ones;
    }
    
    // Alternative approach for three times
    public static int singleNumberIIBitCount(int[] nums) {
        int result = 0;
        
        for (int i = 0; i < 32; i++) {
            int sum = 0;
            
            for (int num : nums) {
                if (((num >> i) & 1) == 1) {
                    sum++;
                }
            }
            
            if (sum % 3 == 1) {
                result |= (1 << i);
            }
        }
        
        return result;
    }
    
    // Two elements appear once, rest appear twice
    public static int[] singleNumberIII(int[] nums) {
        int xor = 0;
        for (int num : nums) {
            xor ^= num;
        }
        
        int rightmostSetBit = xor & (-xor);
        
        int num1 = 0, num2 = 0;
        for (int num : nums) {
            if ((num & rightmostSetBit) != 0) {
                num1 ^= num;
            } else {
                num2 ^= num;
            }
        }
        
        return new int[]{num1, num2};
    }
    
    // Every element appears k times except one appears p times
    public static int singleNumberGeneral(int[] nums, int k, int p) {
        int[] count = new int[32];
        
        for (int num : nums) {
            for (int i = 0; i < 32; i++) {
                count[i] += (num >> i) & 1;
                count[i] %= k;
            }
        }
        
        int result = 0;
        for (int i = 0; i < 32; i++) {
            result += (count[i] << i);
        }
        
        return result;
    }
}
```

---

## Bit Manipulation Algorithm Patterns Summary

### Key Bit Manipulation Techniques:

1. **XOR Properties**
   - `a ^ 0 = a`
   - `a ^ a = 0`
   - `a ^ b ^ b = a`
   - Commutative and Associative

2. **Power of 2 Detection**
   - `n & (n-1) == 0` for powers of 2
   - Removes rightmost set bit

3. **Bit Position Operations**
   - Check: `(n >> i) & 1`
   - Set: `n | (1 << i)`
   - Clear: `n & ~(1 << i)`
   - Toggle: `n ^ (1 << i)`

4. **Counting Set Bits**
   - Brian Kernighan's Algorithm: `n & (n-1)`
   - Built-in: `Integer.bitCount(n)`
   - Lookup table for O(1) per query

5. **Range XOR Pattern**
   - XOR from 1 to n follows 4-cycle pattern
   - `f(n) = n, 1, n+1, 0` for `n%4 = 0,1,2,3`

### Advanced Patterns:

- **Subset Generation**: Use bitmask to represent subsets
- **Two's Complement**: `-n = ~n + 1`
- **Isolate Rightmost Set Bit**: `n & (-n)`
- **Clear Rightmost Set Bit**: `n & (n-1)`
- **Single Number Problems**: XOR properties for duplicates

### Optimization Strategies:

- **Bit Manipulation over Arithmetic**: Often faster
- **Lookup Tables**: Precompute for frequent operations
- **Mathematical Properties**: XOR patterns, powers of 2
- **Space Optimization**: Use bits instead of boolean arrays

### Common Applications:

- **Set Operations**: Union, intersection using bitwise OR/AND
- **Optimization Problems**: Subset enumeration, dynamic programming
- **Cryptography**: XOR encryption, hash functions

---

## Stack and Queue


### 1. Implement Stack using Array
**Time:** O(1) per operation **Space:** O(n)

```java
public class StackUsingArray {
    private int[] arr;
    private int top;
    private int capacity;
    
    public StackUsingArray(int size) {
        arr = new int[size];
        capacity = size;
        top = -1;
    }
    
    public void push(int x) {
        if (top == capacity - 1) {
            System.out.println("Stack Overflow");
            return;
        }
        arr[++top] = x;
    }
    
    public int pop() {
        if (top == -1) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return arr[top--];
    }
    
    public int peek() {
        if (top == -1) {
            System.out.println("Stack is empty");
            return -1;
        }
        return arr[top];
    }
    
    public boolean isEmpty() {
        return top == -1;
    }
    
    public int size() {
        return top + 1;
    }
}
```

### 2. Implement Queue using Array
**Time:** O(1) per operation **Space:** O(n)

```java
public class QueueUsingArray {
    private int[] arr;
    private int front;
    private int rear;
    private int capacity;
    private int count;
    
    public QueueUsingArray(int size) {
        arr = new int[size];
        capacity = size;
        front = 0;
        rear = -1;
        count = 0;
    }
    
    public void push(int x) {
        if (count == capacity) {
            System.out.println("Queue Overflow");
            return;
        }
        rear = (rear + 1) % capacity;
        arr[rear] = x;
        count++;
    }
    
    public int pop() {
        if (count == 0) {
            System.out.println("Queue Underflow");
            return -1;
        }
        int x = arr[front];
        front = (front + 1) % capacity;
        count--;
        return x;
    }
    
    public int peek() {
        if (count == 0) {
            System.out.println("Queue is empty");
            return -1;
        }
        return arr[front];
    }
    
    public boolean isEmpty() {
        return count == 0;
    }
    
    public int size() {
        return count;
    }
}
```

### 3. Implement Stack using Linked List
**Time:** O(1) per operation **Space:** O(n)

```java
public class StackUsingLinkedList {
    private Node head;
    private int size;
    
    private class Node {
        int data;
        Node next;
        
        Node(int data) {
            this.data = data;
        }
    }
    
    public StackUsingLinkedList() {
        head = null;
        size = 0;
    }
    
    public void push(int x) {
        Node newNode = new Node(x);
        newNode.next = head;
        head = newNode;
        size++;
    }
    
    public int pop() {
        if (head == null) {
            System.out.println("Stack Underflow");
            return -1;
        }
        int x = head.data;
        head = head.next;
        size--;
        return x;
    }
    
    public int peek() {
        if (head == null) {
            System.out.println("Stack is empty");
            return -1;
        }
        return head.data;
    }
    
    public boolean isEmpty() {
        return head == null;
    }
    
    public int size() {
        return size;
    }
}
```

### 4. Implement Queue using Linked List
**Time:** O(1) per operation **Space:** O(n)

```java
public class QueueUsingLinkedList {
    private Node front;
    private Node rear;
    private int size;
    
    private class Node {
        int data;
        Node next;
        
        Node(int data) {
            this.data = data;
        }
    }
    
    public QueueUsingLinkedList() {
        front = null;
        rear = null;
        size = 0;
    }
    
    public void push(int x) {
        Node newNode = new Node(x);
        if (rear == null) {
            front = rear = newNode;
        } else {
            rear.next = newNode;
            rear = newNode;
        }
        size++;
    }
    
    public int pop() {
        if (front == null) {
            System.out.println("Queue Underflow");
            return -1;
        }
        int x = front.data;
        front = front.next;
        if (front == null) {
            rear = null;
        }
        size--;
        return x;
    }
    
    public int peek() {
        if (front == null) {
            System.out.println("Queue is empty");
            return -1;
        }
        return front.data;
    }
    
    public boolean isEmpty() {
        return front == null;
    }
    
    public int size() {
        return size;
    }
}
```

### 5. Implement Stack using Queue
**Time:** O(n) push, O(1) pop **Space:** O(n)

```java
import java.util.*;

public class StackUsingQueue {
    private Queue<Integer> q;
    
    public StackUsingQueue() {
        q = new LinkedList<>();
    }
    
    public void push(int x) {
        int size = q.size();
        q.offer(x);
        for (int i = 0; i < size; i++) {
            q.offer(q.poll());
        }
    }
    
    public int pop() {
        if (q.isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return q.poll();
    }
    
    public int top() {
        if (q.isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return q.peek();
    }
    
    public boolean empty() {
        return q.isEmpty();
    }
}
```

### 6. Implement Queue using Stack (Method 1)
**Time:** O(n) push, O(1) pop **Space:** O(n)

```java
import java.util.*;

public class QueueUsingStackMethod1 {
    private Stack<Integer> input;
    private Stack<Integer> output;
    
    public QueueUsingStackMethod1() {
        input = new Stack<>();
        output = new Stack<>();
    }
    
    public void push(int x) {
        while (!input.isEmpty()) {
            output.push(input.pop());
        }
        input.push(x);
        while (!output.isEmpty()) {
            input.push(output.pop());
        }
    }
    
    public int pop() {
        if (input.isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return input.pop();
    }
    
    public int peek() {
        if (input.isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return input.peek();
    }
    
    public boolean empty() {
        return input.isEmpty();
    }
}
```

### 7. Implement Queue using Stack (Method 2)
**Time:** O(1) push, O(1) pop amortized **Space:** O(n)

```java
import java.util.*;

public class QueueUsingStackMethod2 {
    private Stack<Integer> input;
    private Stack<Integer> output;
    
    public QueueUsingStackMethod2() {
        input = new Stack<>();
        output = new Stack<>();
    }
    
    public void push(int x) {
        input.push(x);
    }
    
    public int pop() {
        if (output.isEmpty()) {
            while (!input.isEmpty()) {
                output.push(input.pop());
            }
        }
        if (output.isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return output.pop();
    }
    
    public int peek() {
        if (output.isEmpty()) {
            while (!input.isEmpty()) {
                output.push(input.pop());
            }
        }
        if (output.isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return output.peek();
    }
    
    public boolean empty() {
        return input.isEmpty() && output.isEmpty();
    }
}
```

### 8. Check for Balanced Parentheses
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class BalancedParentheses {
    public static boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        
        for (char c : s.toCharArray()) {
            if (c == '(' || c == '[' || c == '{') {
                stack.push(c);
            } else {
                if (stack.isEmpty()) return false;
                
                char top = stack.pop();
                if ((c == ')' && top != '(') ||
                    (c == ']' && top != '[') ||
                    (c == '}' && top != '{')) {
                    return false;
                }
            }
        }
        
        return stack.isEmpty();
    }
    
    public static boolean isValidOptimized(String s) {
        Stack<Character> stack = new Stack<>();
        
        for (char c : s.toCharArray()) {
            if (c == '(') stack.push(')');
            else if (c == '[') stack.push(']');
            else if (c == '{') stack.push('}');
            else if (stack.isEmpty() || stack.pop() != c) return false;
        }
        
        return stack.isEmpty();
    }
}
```

### 9. Infix to Postfix Conversion
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class InfixToPostfix {
    public static int precedence(char c) {
        if (c == '^') return 3;
        if (c == '*' || c == '/') return 2;
        if (c == '+' || c == '-') return 1;
        return -1;
    }
    
    public static String infixToPostfix(String s) {
        Stack<Character> stack = new Stack<>();
        StringBuilder result = new StringBuilder();
        
        for (char c : s.toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                result.append(c);
            } else if (c == '(') {
                stack.push(c);
            } else if (c == ')') {
                while (!stack.isEmpty() && stack.peek() != '(') {
                    result.append(stack.pop());
                }
                stack.pop();
            } else {
                while (!stack.isEmpty() && precedence(c) <= precedence(stack.peek())) {
                    result.append(stack.pop());
                }
                stack.push(c);
            }
        }
        
        while (!stack.isEmpty()) {
            result.append(stack.pop());
        }
        
        return result.toString();
    }
}
```

### 10. Infix to Prefix Conversion
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class InfixToPrefix {
    public static int precedence(char c) {
        if (c == '^') return 3;
        if (c == '*' || c == '/') return 2;
        if (c == '+' || c == '-') return 1;
        return -1;
    }
    
    public static String infixToPrefix(String s) {
        StringBuilder reversed = new StringBuilder(s).reverse();
        
        for (int i = 0; i < reversed.length(); i++) {
            if (reversed.charAt(i) == '(') {
                reversed.setCharAt(i, ')');
            } else if (reversed.charAt(i) == ')') {
                reversed.setCharAt(i, '(');
            }
        }
        
        Stack<Character> stack = new Stack<>();
        StringBuilder result = new StringBuilder();
        
        for (char c : reversed.toString().toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                result.append(c);
            } else if (c == '(') {
                stack.push(c);
            } else if (c == ')') {
                while (!stack.isEmpty() && stack.peek() != '(') {
                    result.append(stack.pop());
                }
                stack.pop();
            } else {
                if (c == '^') {
                    while (!stack.isEmpty() && precedence(c) <= precedence(stack.peek())) {
                        result.append(stack.pop());
                    }
                } else {
                    while (!stack.isEmpty() && precedence(c) < precedence(stack.peek())) {
                        result.append(stack.pop());
                    }
                }
                stack.push(c);
            }
        }
        
        while (!stack.isEmpty()) {
            result.append(stack.pop());
        }
        
        return result.reverse().toString();
    }
}
```

### 11. Postfix to Infix Conversion
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class PostfixToInfix {
    public static String postfixToInfix(String s) {
        Stack<String> stack = new Stack<>();
        
        for (char c : s.toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                stack.push(String.valueOf(c));
            } else {
                String op2 = stack.pop();
                String op1 = stack.pop();
                String result = "(" + op1 + c + op2 + ")";
                stack.push(result);
            }
        }
        
        return stack.pop();
    }
}
```

### 12. Next Greater Element I
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class NextGreaterElement1 {
    public static int[] nextGreaterElement(int[] nums1, int[] nums2) {
        Map<Integer, Integer> map = new HashMap<>();
        Stack<Integer> stack = new Stack<>();
        
        for (int num : nums2) {
            while (!stack.isEmpty() && stack.peek() < num) {
                map.put(stack.pop(), num);
            }
            stack.push(num);
        }
        
        int[] result = new int[nums1.length];
        for (int i = 0; i < nums1.length; i++) {
            result[i] = map.getOrDefault(nums1[i], -1);
        }
        
        return result;
    }
}
```

### 13. Next Greater Element II (Circular Array)
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class NextGreaterElement2 {
    public static int[] nextGreaterElements(int[] nums) {
        int n = nums.length;
        int[] result = new int[n];
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 2 * n - 1; i >= 0; i--) {
            while (!stack.isEmpty() && stack.peek() <= nums[i % n]) {
                stack.pop();
            }
            
            if (i < n) {
                result[i] = stack.isEmpty() ? -1 : stack.peek();
            }
            
            stack.push(nums[i % n]);
        }
        
        return result;
    }
}
```

### 14. Previous Smaller Element
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class PreviousSmallerElement {
    public static int[] previousSmaller(int[] arr) {
        int n = arr.length;
        int[] result = new int[n];
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && stack.peek() >= arr[i]) {
                stack.pop();
            }
            
            result[i] = stack.isEmpty() ? -1 : stack.peek();
            stack.push(arr[i]);
        }
        
        return result;
    }
}
```

### 15. Number of NGEs to the Right
**Time:** O(n²) **Space:** O(1)

```java
public class NumberOfNGEs {
    public static int[] count_NGE(int n, int[] arr, int[] queries) {
        int[] result = new int[queries.length];
        
        for (int q = 0; q < queries.length; q++) {
            int index = queries[q];
            int count = 0;
            
            for (int i = index + 1; i < n; i++) {
                if (arr[i] > arr[index]) {
                    count++;
                }
            }
            
            result[q] = count;
        }
        
        return result;
    }
}
```

### 16. Trapping Rain Water
**Time:** O(n) **Space:** O(1)

```java
public class TrappingRainWater {
    public static int trap(int[] height) {
        if (height.length == 0) return 0;
        
        int left = 0, right = height.length - 1;
        int leftMax = 0, rightMax = 0;
        int water = 0;
        
        while (left < right) {
            if (height[left] < height[right]) {
                if (height[left] >= leftMax) {
                    leftMax = height[left];
                } else {
                    water += leftMax - height[left];
                }
                left++;
            } else {
                if (height[right] >= rightMax) {
                    rightMax = height[right];
                } else {
                    water += rightMax - height[right];
                }
                right--;
            }
        }
        
        return water;
    }
    
    public static int trapUsingStack(int[] height) {
        Stack<Integer> stack = new Stack<>();
        int water = 0;
        
        for (int i = 0; i < height.length; i++) {
            while (!stack.isEmpty() && height[i] > height[stack.peek()]) {
                int top = stack.pop();
                if (stack.isEmpty()) break;
                
                int distance = i - stack.peek() - 1;
                int boundedHeight = Math.min(height[i], height[stack.peek()]) - height[top];
                water += distance * boundedHeight;
            }
            stack.push(i);
        }
        
        return water;
    }
}
```

### 17. Sum of Subarray Minimums
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class SumSubarrayMinimums {
    public static int sumSubarrayMins(int[] arr) {
        int MOD = 1000000007;
        int n = arr.length;
        
        int[] left = new int[n];
        int[] right = new int[n];
        
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && arr[stack.peek()] > arr[i]) {
                stack.pop();
            }
            left[i] = stack.isEmpty() ? -1 : stack.peek();
            stack.push(i);
        }
        
        stack.clear();
        
        for (int i = n - 1; i >= 0; i--) {
            while (!stack.isEmpty() && arr[stack.peek()] >= arr[i]) {
                stack.pop();
            }
            right[i] = stack.isEmpty() ? n : stack.peek();
            stack.push(i);
        }
        
        long result = 0;
        for (int i = 0; i < n; i++) {
            long leftCount = i - left[i];
            long rightCount = right[i] - i;
            result = (result + (leftCount * rightCount % MOD) * arr[i] % MOD) % MOD;
        }
        
        return (int) result;
    }
}
```

### 18. Asteroid Collision
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class AsteroidCollision {
    public static int[] asteroidCollision(int[] asteroids) {
        Stack<Integer> stack = new Stack<>();
        
        for (int asteroid : asteroids) {
            boolean destroyed = false;
            
            while (!stack.isEmpty() && asteroid < 0 && stack.peek() > 0) {
                if (stack.peek() < -asteroid) {
                    stack.pop();
                } else if (stack.peek() == -asteroid) {
                    stack.pop();
                    destroyed = true;
                    break;
                } else {
                    destroyed = true;
                    break;
                }
            }
            
            if (!destroyed) {
                stack.push(asteroid);
            }
        }
        
        int[] result = new int[stack.size()];
        for (int i = result.length - 1; i >= 0; i--) {
            result[i] = stack.pop();
        }
        
        return result;
    }
}
```

### 19. Sum of Subarray Ranges
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class SumSubarrayRanges {
    public static long subArrayRanges(int[] nums) {
        return sumSubarrayMaximums(nums) - sumSubarrayMinimums(nums);
    }
    
    private static long sumSubarrayMaximums(int[] arr) {
        int n = arr.length;
        int[] left = new int[n];
        int[] right = new int[n];
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && arr[stack.peek()] <= arr[i]) {
                stack.pop();
            }
            left[i] = stack.isEmpty() ? -1 : stack.peek();
            stack.push(i);
        }
        
        stack.clear();
        
        for (int i = n - 1; i >= 0; i--) {
            while (!stack.isEmpty() && arr[stack.peek()] < arr[i]) {
                stack.pop();
            }
            right[i] = stack.isEmpty() ? n : stack.peek();
            stack.push(i);
        }
        
        long result = 0;
        for (int i = 0; i < n; i++) {
            result += (long) (i - left[i]) * (right[i] - i) * arr[i];
        }
        
        return result;
    }
    
    private static long sumSubarrayMinimums(int[] arr) {
        int n = arr.length;
        int[] left = new int[n];
        int[] right = new int[n];
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && arr[stack.peek()] > arr[i]) {
                stack.pop();
            }
            left[i] = stack.isEmpty() ? -1 : stack.peek();
            stack.push(i);
        }
        
        stack.clear();
        
        for (int i = n - 1; i >= 0; i--) {
            while (!stack.isEmpty() && arr[stack.peek()] >= arr[i]) {
                stack.pop();
            }
            right[i] = stack.isEmpty() ? n : stack.peek();
            stack.push(i);
        }
        
        long result = 0;
        for (int i = 0; i < n; i++) {
            result += (long) (i - left[i]) * (right[i] - i) * arr[i];
        }
        
        return result;
    }
}
```

### 20. Remove K Digits
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class RemoveKDigits {
    public static String removeKdigits(String num, int k) {
        Stack<Character> stack = new Stack<>();
        
        for (char digit : num.toCharArray()) {
            while (k > 0 && !stack.isEmpty() && stack.peek() > digit) {
                stack.pop();
                k--;
            }
            stack.push(digit);
        }
        
        while (k > 0) {
            stack.pop();
            k--;
        }
        
        StringBuilder result = new StringBuilder();
        while (!stack.isEmpty()) {
            result.append(stack.pop());
        }
        result.reverse();
        
        while (result.length() > 1 && result.charAt(0) == '0') {
            result.deleteCharAt(0);
        }
        
        return result.length() == 0 ? "0" : result.toString();
    }
}
```

### 21. Largest Rectangle in Histogram
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class LargestRectangleHistogram {
    public static int largestRectangleArea(int[] heights) {
        Stack<Integer> stack = new Stack<>();
        int maxArea = 0;
        
        for (int i = 0; i <= heights.length; i++) {
            int h = (i == heights.length) ? 0 : heights[i];
            
            while (!stack.isEmpty() && h < heights[stack.peek()]) {
                int height = heights[stack.pop()];
                int width = stack.isEmpty() ? i : i - stack.peek() - 1;
                maxArea = Math.max(maxArea, height * width);
            }
            
            stack.push(i);
        }
        
        return maxArea;
    }
    
    public static int largestRectangleAreaOptimized(int[] heights) {
        int n = heights.length;
        int[] leftSmaller = new int[n];
        int[] rightSmaller = new int[n];
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && heights[stack.peek()] >= heights[i]) {
                stack.pop();
            }
            leftSmaller[i] = stack.isEmpty() ? 0 : stack.peek() + 1;
            stack.push(i);
        }
        
        stack.clear();
        
        for (int i = n - 1; i >= 0; i--) {
            while (!stack.isEmpty() && heights[stack.peek()] >= heights[i]) {
                stack.pop();
            }
            rightSmaller[i] = stack.isEmpty() ? n - 1 : stack.peek() - 1;
            stack.push(i);
        }
        
        int maxArea = 0;
        for (int i = 0; i < n; i++) {
            maxArea = Math.max(maxArea, heights[i] * (rightSmaller[i] - leftSmaller[i] + 1));
        }
        
        return maxArea;
    }
}
```

### 22. Maximal Rectangle
**Time:** O(n × m) **Space:** O(m)

```java
import java.util.*;

public class MaximalRectangle {
    public static int maximalRectangle(char[][] matrix) {
        if (matrix.length == 0) return 0;
        
        int n = matrix.length;
        int m = matrix[0].length;
        int[] heights = new int[m];
        int maxArea = 0;
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (matrix[i][j] == '1') {
                    heights[j]++;
                } else {
                    heights[j] = 0;
                }
            }
            maxArea = Math.max(maxArea, largestRectangleArea(heights));
        }
        
        return maxArea;
    }
    
    private static int largestRectangleArea(int[] heights) {
        Stack<Integer> stack = new Stack<>();
        int maxArea = 0;
        
        for (int i = 0; i <= heights.length; i++) {
            int h = (i == heights.length) ? 0 : heights[i];
            
            while (!stack.isEmpty() && h < heights[stack.peek()]) {
                int height = heights[stack.pop()];
                int width = stack.isEmpty() ? i : i - stack.peek() - 1;
                maxArea = Math.max(maxArea, height * width);
            }
            
            stack.push(i);
        }
        
        return maxArea;
    }
}
```

### 23. Sliding Window Maximum
**Time:** O(n) **Space:** O(k)

```java
import java.util.*;

public class SlidingWindowMaximum {
    public static int[] maxSlidingWindow(int[] nums, int k) {
        Deque<Integer> deque = new ArrayDeque<>();
        int n = nums.length;
        int[] result = new int[n - k + 1];
        
        for (int i = 0; i < n; i++) {
            while (!deque.isEmpty() && deque.peekFirst() < i - k + 1) {
                deque.pollFirst();
            }
            
            while (!deque.isEmpty() && nums[deque.peekLast()] <= nums[i]) {
                deque.pollLast();
            }
            
            deque.offerLast(i);
            
            if (i >= k - 1) {
                result[i - k + 1] = nums[deque.peekFirst()];
            }
        }
        
        return result;
    }
    
    public static int[] maxSlidingWindowBruteForce(int[] nums, int k) {
        int n = nums.length;
        int[] result = new int[n - k + 1];
        
        for (int i = 0; i <= n - k; i++) {
            int max = nums[i];
            for (int j = i + 1; j < i + k; j++) {
                max = Math.max(max, nums[j]);
            }
            result[i] = max;
        }
        
        return result;
    }
}
```

### 24. LRU Cache
**Time:** O(1) **Space:** O(capacity)

```java
import java.util.*;

public class LRUCache {
    class Node {
        int key;
        int val;
        Node prev;
        Node next;
        
        Node(int key, int val) {
            this.key = key;
            this.val = val;
        }
    }
    
    private Map<Integer, Node> cache = new HashMap<>();
    private int capacity;
    private Node left;
    private Node right;
    
    public LRUCache(int capacity) {
        this.capacity = capacity;
        
        left = new Node(0, 0);
        right = new Node(0, 0);
        left.next = right;
        right.prev = left;
    }
    
    private void remove(Node node) {
        Node prevNode = node.prev;
        Node nextNode = node.next;
        prevNode.next = nextNode;
        nextNode.prev = prevNode;
    }
    
    private void insert(Node node) {
        Node prevNode = right.prev;
        Node nextNode = right;
        
        prevNode.next = node;
        nextNode.prev = node;
        node.next = nextNode;
        node.prev = prevNode;
    }
    
    public int get(int key) {
        if (cache.containsKey(key)) {
            remove(cache.get(key));
            insert(cache.get(key));
            return cache.get(key).val;
        }
        return -1;
    }
    
    public void put(int key, int value) {
        if (cache.containsKey(key)) {
            remove(cache.get(key));
        }
        cache.put(key, new Node(key, value));
        insert(cache.get(key));
        
        if (cache.size() > capacity) {
            Node lru = left.next;
            remove(lru);
            cache.remove(lru.key);
        }
    }
}
```

### 25. LFU Cache
**Time:** O(1) **Space:** O(capacity)

```java
import java.util.*;

public class LFUCache {
    class Node {
        int key, val, freq;
        Node prev, next;
        
        Node(int key, int val) {
            this.key = key;
            this.val = val;
            this.freq = 1;
        }
    }
    
    class DLL {
        Node head, tail;
        int size;
        
        DLL() {
            head = new Node(0, 0);
            tail = new Node(0, 0);
            head.next = tail;
            tail.prev = head;
        }
        
        void addNode(Node node) {
            Node temp = head.next;
            node.next = temp;
            node.prev = head;
            head.next = node;
            temp.prev = node;
            size++;
        }
        
        void removeNode(Node node) {
            Node prev = node.prev;
            Node next = node.next;
            prev.next = next;
            next.prev = prev;
            size--;
        }
    }
    
    private Map<Integer, Node> cache;
    private Map<Integer, DLL> freqMap;
    private int capacity;
    private int minFreq;
    
    public LFUCache(int capacity) {
        this.capacity = capacity;
        cache = new HashMap<>();
        freqMap = new HashMap<>();
        minFreq = 0;
    }
    
    private void updateFreq(Node node) {
        int freq = node.freq;
        DLL list = freqMap.get(freq);
        list.removeNode(node);
        
        if (freq == minFreq && list.size == 0) {
            minFreq++;
        }
        
        node.freq++;
        freqMap.computeIfAbsent(node.freq, k -> new DLL()).addNode(node);
    }
    
    public int get(int key) {
        if (!cache.containsKey(key)) return -1;
        
        Node node = cache.get(key);
        updateFreq(node);
        return node.val;
    }
    
    public void put(int key, int value) {
        if (capacity == 0) return;
        
        if (cache.containsKey(key)) {
            Node node = cache.get(key);
            node.val = value;
            updateFreq(node);
        } else {
            if (cache.size() >= capacity) {
                DLL list = freqMap.get(minFreq);
                Node toRemove = list.tail.prev;
                list.removeNode(toRemove);
                cache.remove(toRemove.key);
            }
            
            Node newNode = new Node(key, value);
            cache.put(key, newNode);
            freqMap.computeIfAbsent(1, k -> new DLL()).addNode(newNode);
            minFreq = 1;
        }
    }
}
```

---


## Sliding Window & Two Pointer

### 1. Maximum Sum of Subarray of Size K
**Time:** O(n) **Space:** O(1)

```java
public class MaxSumSubarray {
    public static int maxSumSubarray(int[] arr, int k) {
        int n = arr.length;
        if (n < k) return -1;
        
        int windowSum = 0;
        for (int i = 0; i < k; i++) {
            windowSum += arr[i];
        }
        
        int maxSum = windowSum;
        for (int i = k; i < n; i++) {
            windowSum += arr[i] - arr[i - k];
            maxSum = Math.max(maxSum, windowSum);
        }
        
        return maxSum;
    }
}
```

### 2. First Negative Number in Every Window of Size K
**Time:** O(n) **Space:** O(k)

```java
import java.util.*;

public class FirstNegativeInWindow {
    public static long[] printFirstNegativeInteger(long[] arr, int n, int k) {
        long[] result = new long[n - k + 1];
        Queue<Integer> queue = new LinkedList<>();
        
        for (int i = 0; i < k; i++) {
            if (arr[i] < 0) {
                queue.offer(i);
            }
        }
        
        for (int i = k; i <= n; i++) {
            if (!queue.isEmpty() && queue.peek() < i - k) {
                queue.poll();
            }
            
            result[i - k] = queue.isEmpty() ? 0 : arr[queue.peek()];
            
            if (i < n && arr[i] < 0) {
                queue.offer(i);
            }
        }
        
        return result;
    }
}
```

### 3. Count Occurrences of Anagram
**Time:** O(n) **Space:** O(1)

```java
public class CountAnagrams {
    public static int search(String pat, String txt) {
        int[] patCount = new int[26];
        int[] windowCount = new int[26];
        
        for (char c : pat.toCharArray()) {
            patCount[c - 'a']++;
        }
        
        int windowSize = pat.length();
        int result = 0;
        
        for (int i = 0; i < txt.length(); i++) {
            windowCount[txt.charAt(i) - 'a']++;
            
            if (i >= windowSize) {
                windowCount[txt.charAt(i - windowSize) - 'a']--;
            }
            
            if (i >= windowSize - 1) {
                if (Arrays.equals(patCount, windowCount)) {
                    result++;
                }
            }
        }
        
        return result;
    }
}
```

### 4. Maximum of All Subarrays of Size K
**Time:** O(n) **Space:** O(k)

```java
import java.util.*;

public class MaxInWindow {
    public static int[] maxSlidingWindow(int[] nums, int k) {
        Deque<Integer> deque = new ArrayDeque<>();
        int n = nums.length;
        int[] result = new int[n - k + 1];
        
        for (int i = 0; i < n; i++) {
            while (!deque.isEmpty() && deque.peekFirst() < i - k + 1) {
                deque.pollFirst();
            }
            
            while (!deque.isEmpty() && nums[deque.peekLast()] <= nums[i]) {
                deque.pollLast();
            }
            
            deque.offerLast(i);
            
            if (i >= k - 1) {
                result[i - k + 1] = nums[deque.peekFirst()];
            }
        }
        
        return result;
    }
}
```

### 5. Longest Subarray with Sum K (Positive Numbers)
**Time:** O(n) **Space:** O(1)

```java
public class LongestSubarrayWithSumK {
    public static int lenOfLongSubarr(int[] arr, int n, int k) {
        int left = 0, right = 0;
        int sum = 0;
        int maxLen = 0;
        
        while (right < n) {
            sum += arr[right];
            
            while (left <= right && sum > k) {
                sum -= arr[left];
                left++;
            }
            
            if (sum == k) {
                maxLen = Math.max(maxLen, right - left + 1);
            }
            
            right++;
        }
        
        return maxLen;
    }
    
    public static int lenOfLongSubarrWithNegatives(int[] arr, int n, int k) {
        Map<Integer, Integer> prefixSumMap = new HashMap<>();
        int sum = 0;
        int maxLen = 0;
        
        for (int i = 0; i < n; i++) {
            sum += arr[i];
            
            if (sum == k) {
                maxLen = i + 1;
            }
            
            if (prefixSumMap.containsKey(sum - k)) {
                maxLen = Math.max(maxLen, i - prefixSumMap.get(sum - k));
            }
            
            if (!prefixSumMap.containsKey(sum)) {
                prefixSumMap.put(sum, i);
            }
        }
        
        return maxLen;
    }
}
```

### 6. Longest Substring Without Repeating Characters
**Time:** O(n) **Space:** O(min(m, n))

```java
import java.util.*;

public class LongestUniqueSubstring {
    public static int lengthOfLongestSubstring(String s) {
        Set<Character> set = new HashSet<>();
        int left = 0;
        int maxLength = 0;
        
        for (int right = 0; right < s.length(); right++) {
            while (set.contains(s.charAt(right))) {
                set.remove(s.charAt(left));
                left++;
            }
            
            set.add(s.charAt(right));
            maxLength = Math.max(maxLength, right - left + 1);
        }
        
        return maxLength;
    }
    
    public static int lengthOfLongestSubstringOptimized(String s) {
        Map<Character, Integer> map = new HashMap<>();
        int left = 0;
        int maxLength = 0;
        
        for (int right = 0; right < s.length(); right++) {
            if (map.containsKey(s.charAt(right))) {
                left = Math.max(left, map.get(s.charAt(right)) + 1);
            }
            
            map.put(s.charAt(right), right);
            maxLength = Math.max(maxLength, right - left + 1);
        }
        
        return maxLength;
    }
}
```

### 7. Max Consecutive Ones III
**Time:** O(n) **Space:** O(1)

```java
public class MaxConsecutiveOnes {
    public static int longestOnes(int[] nums, int k) {
        int left = 0;
        int zeros = 0;
        int maxLength = 0;
        
        for (int right = 0; right < nums.length; right++) {
            if (nums[right] == 0) {
                zeros++;
            }
            
            while (zeros > k) {
                if (nums[left] == 0) {
                    zeros--;
                }
                left++;
            }
            
            maxLength = Math.max(maxLength, right - left + 1);
        }
        
        return maxLength;
    }
}
```

### 8. Fruit Into Baskets
**Time:** O(n) **Space:** O(1)

```java
import java.util.*;

public class FruitBaskets {
    public static int totalFruit(int[] fruits) {
        Map<Integer, Integer> basket = new HashMap<>();
        int left = 0;
        int maxFruits = 0;
        
        for (int right = 0; right < fruits.length; right++) {
            basket.put(fruits[right], basket.getOrDefault(fruits[right], 0) + 1);
            
            while (basket.size() > 2) {
                basket.put(fruits[left], basket.get(fruits[left]) - 1);
                if (basket.get(fruits[left]) == 0) {
                    basket.remove(fruits[left]);
                }
                left++;
            }
            
            maxFruits = Math.max(maxFruits, right - left + 1);
        }
        
        return maxFruits;
    }
}
```

### 9. Longest Substring with At Most K Distinct Characters
**Time:** O(n) **Space:** O(k)

```java
import java.util.*;

public class LongestSubstringKDistinct {
    public static int lengthOfLongestSubstringKDistinct(String s, int k) {
        if (k == 0) return 0;
        
        Map<Character, Integer> windowCount = new HashMap<>();
        int left = 0;
        int maxLength = 0;
        
        for (int right = 0; right < s.length(); right++) {
            char rightChar = s.charAt(right);
            windowCount.put(rightChar, windowCount.getOrDefault(rightChar, 0) + 1);
            
            while (windowCount.size() > k) {
                char leftChar = s.charAt(left);
                windowCount.put(leftChar, windowCount.get(leftChar) - 1);
                if (windowCount.get(leftChar) == 0) {
                    windowCount.remove(leftChar);
                }
                left++;
            }
            
            maxLength = Math.max(maxLength, right - left + 1);
        }
        
        return maxLength;
    }
}
```

### 10. Number of Substrings Containing All Three Characters
**Time:** O(n) **Space:** O(1)

```java
public class SubstringsWithThreeChars {
    public static int numberOfSubstrings(String s) {
        int[] lastSeen = {-1, -1, -1};
        int count = 0;
        
        for (int i = 0; i < s.length(); i++) {
            lastSeen[s.charAt(i) - 'a'] = i;
            
            if (lastSeen[0] != -1 && lastSeen[1] != -1 && lastSeen[2] != -1) {
                count += Math.min(lastSeen[0], Math.min(lastSeen[1], lastSeen[2])) + 1;
            }
        }
        
        return count;
    }
}
```

### 11. Two Sum (Sorted Array)
**Time:** O(n) **Space:** O(1)

```java
public class TwoSum {
    public static int[] twoSum(int[] numbers, int target) {
        int left = 0;
        int right = numbers.length - 1;
        
        while (left < right) {
            int sum = numbers[left] + numbers[right];
            
            if (sum == target) {
                return new int[]{left + 1, right + 1};
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }
        
        return new int[]{-1, -1};
    }
    
    public static boolean hasTwoSum(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;
        
        while (left < right) {
            int sum = arr[left] + arr[right];
            
            if (sum == target) {
                return true;
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }
        
        return false;
    }
}
```

### 12. 3Sum
**Time:** O(n²) **Space:** O(1)

```java
import java.util.*;

public class ThreeSum {
    public static List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);
        
        for (int i = 0; i < nums.length - 2; i++) {
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            
            int left = i + 1;
            int right = nums.length - 1;
            
            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];
                
                if (sum == 0) {
                    result.add(Arrays.asList(nums[i], nums[left], nums[right]));
                    
                    while (left < right && nums[left] == nums[left + 1]) left++;
                    while (left < right && nums[right] == nums[right - 1]) right--;
                    
                    left++;
                    right--;
                } else if (sum < 0) {
                    left++;
                } else {
                    right--;
                }
            }
        }
        
        return result;
    }
}
```

### 13. 4Sum
**Time:** O(n³) **Space:** O(1)

```java
import java.util.*;

public class FourSum {
    public static List<List<Integer>> fourSum(int[] nums, int target) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);
        int n = nums.length;
        
        for (int i = 0; i < n - 3; i++) {
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            
            for (int j = i + 1; j < n - 2; j++) {
                if (j > i + 1 && nums[j] == nums[j - 1]) continue;
                
                int left = j + 1;
                int right = n - 1;
                
                while (left < right) {
                    long sum = (long) nums[i] + nums[j] + nums[left] + nums[right];
                    
                    if (sum == target) {
                        result.add(Arrays.asList(nums[i], nums[j], nums[left], nums[right]));
                        
                        while (left < right && nums[left] == nums[left + 1]) left++;
                        while (left < right && nums[right] == nums[right - 1]) right--;
                        
                        left++;
                        right--;
                    } else if (sum < target) {
                        left++;
                    } else {
                        right--;
                    }
                }
            }
        }
        
        return result;
    }
}
```

### 14. Minimum Window Substring
**Time:** O(|s| + |t|) **Space:** O(|s| + |t|)

```java
import java.util.*;

public class MinWindowSubstring {
    public static String minWindow(String s, String t) {
        if (s.length() == 0 || t.length() == 0) return "";
        
        Map<Character, Integer> dictT = new HashMap<>();
        for (char c : t.toCharArray()) {
            dictT.put(c, dictT.getOrDefault(c, 0) + 1);
        }
        
        int required = dictT.size();
        int left = 0, right = 0;
        int formed = 0;
        
        Map<Character, Integer> windowCounts = new HashMap<>();
        
        int[] ans = {-1, 0, 0};
        
        while (right < s.length()) {
            char character = s.charAt(right);
            windowCounts.put(character, windowCounts.getOrDefault(character, 0) + 1);
            
            if (dictT.containsKey(character) && 
                windowCounts.get(character).intValue() == dictT.get(character).intValue()) {
                formed++;
            }
            
            while (left <= right && formed == required) {
                character = s.charAt(left);
                
                if (ans[0] == -1 || right - left + 1 < ans[0]) {
                    ans[0] = right - left + 1;
                    ans[1] = left;
                    ans[2] = right;
                }
                
                windowCounts.put(character, windowCounts.get(character) - 1);
                if (dictT.containsKey(character) && 
                    windowCounts.get(character).intValue() < dictT.get(character).intValue()) {
                    formed--;
                }
                
                left++;
            }
            
            right++;
        }
        
        return ans[0] == -1 ? "" : s.substring(ans[1], ans[2] + 1);
    }
}
```

### 15. Subarrays with K Different Integers
**Time:** O(n) **Space:** O(k)

```java
import java.util.*;

public class SubarraysWithKDistinct {
    public static int subarraysWithKDistinct(int[] nums, int k) {
        return atMostK(nums, k) - atMostK(nums, k - 1);
    }
    
    private static int atMostK(int[] nums, int k) {
        Map<Integer, Integer> count = new HashMap<>();
        int left = 0;
        int result = 0;
        
        for (int right = 0; right < nums.length; right++) {
            if (count.getOrDefault(nums[right], 0) == 0) {
                k--;
            }
            count.put(nums[right], count.getOrDefault(nums[right], 0) + 1);
            
            while (k < 0) {
                count.put(nums[left], count.get(nums[left]) - 1);
                if (count.get(nums[left]) == 0) {
                    k++;
                }
                left++;
            }
            
            result += right - left + 1;
        }
        
        return result;
    }
}
```

### 16. Binary Subarrays with Sum
**Time:** O(n) **Space:** O(1)

```java
public class BinarySubarraysWithSum {
    public static int numSubarraysWithSum(int[] nums, int goal) {
        return atMost(nums, goal) - atMost(nums, goal - 1);
    }
    
    private static int atMost(int[] nums, int goal) {
        if (goal < 0) return 0;
        
        int left = 0;
        int sum = 0;
        int result = 0;
        
        for (int right = 0; right < nums.length; right++) {
            sum += nums[right];
            
            while (sum > goal) {
                sum -= nums[left];
                left++;
            }
            
            result += right - left + 1;
        }
        
        return result;
    }
}
```

---

## Template Patterns

### Fixed Window Template
```java
public int fixedWindow(int[] arr, int k) {
    int windowSum = 0;
    
    for (int i = 0; i < k; i++) {
        windowSum += arr[i];
    }
    
    int result = windowSum;
    
    for (int i = k; i < arr.length; i++) {
        windowSum += arr[i] - arr[i - k];
        result = Math.max(result, windowSum);
    }
    
    return result;
}
```

### Variable Window Template
```java
public int variableWindow(int[] arr, int target) {
    int left = 0;
    int sum = 0;
    int result = 0;
    
    for (int right = 0; right < arr.length; right++) {
        sum += arr[right];
        
        while (sum > target) {
            sum -= arr[left];
            left++;
        }
        
        result = Math.max(result, right - left + 1);
    }
    
    return result;
}
```

### Two Pointers Template
```java
public boolean twoPointers(int[] arr, int target) {
    int left = 0;
    int right = arr.length - 1;
    
    while (left < right) {
        int sum = arr[left] + arr[right];
        
        if (sum == target) {
            return true;
        } else if (sum < target) {
            left++;
        } else {
            right--;
        }
    }
    
    return false;
}
```

---


## Heaps

### Min Heap Implementation
```java
import java.util.*;

class MinHeap {
    private List<Integer> heap;
    
    public MinHeap() {
        heap = new ArrayList<>();
    }
    
    public void insert(int val) {
        heap.add(val);
        heapifyUp(heap.size() - 1);
    }
    
    public int extractMin() {
        int min = heap.get(0);
        heap.set(0, heap.get(heap.size() - 1));
        heap.remove(heap.size() - 1);
        heapifyDown(0);
        return min;
    }
    
    private void heapifyUp(int index) {
        while (index > 0) {
            int parent = (index - 1) / 2;
            if (heap.get(index) >= heap.get(parent)) break;
            swap(index, parent);
            index = parent;
        }
    }
    
    private void heapifyDown(int index) {
        while (true) {
            int left = 2 * index + 1;
            int right = 2 * index + 2;
            int smallest = index;
            
            if (left < heap.size() && heap.get(left) < heap.get(smallest)) {
                smallest = left;
            }
            if (right < heap.size() && heap.get(right) < heap.get(smallest)) {
                smallest = right;
            }
            
            if (smallest == index) break;
            swap(index, smallest);
            index = smallest;
        }
    }
    
    private void swap(int i, int j) {
        int temp = heap.get(i);
        heap.set(i, heap.get(j));
        heap.set(j, temp);
    }
    
    public boolean isEmpty() {
        return heap.isEmpty();
    }
    
    public int size() {
        return heap.size();
    }
}
```

### Max Heap Implementation
```java
class MaxHeap {
    private List<Integer> heap;
    
    public MaxHeap() {
        heap = new ArrayList<>();
    }
    
    public void insert(int val) {
        heap.add(val);
        heapifyUp(heap.size() - 1);
    }
    
    public int extractMax() {
        int max = heap.get(0);
        heap.set(0, heap.get(heap.size() - 1));
        heap.remove(heap.size() - 1);
        heapifyDown(0);
        return max;
    }
    
    private void heapifyUp(int index) {
        while (index > 0) {
            int parent = (index - 1) / 2;
            if (heap.get(index) <= heap.get(parent)) break;
            swap(index, parent);
            index = parent;
        }
    }
    
    private void heapifyDown(int index) {
        while (true) {
            int left = 2 * index + 1;
            int right = 2 * index + 2;
            int largest = index;
            
            if (left < heap.size() && heap.get(left) > heap.get(largest)) {
                largest = left;
            }
            if (right < heap.size() && heap.get(right) > heap.get(largest)) {
                largest = right;
            }
            
            if (largest == index) break;
            swap(index, largest);
            index = largest;
        }
    }
    
    private void swap(int i, int j) {
        int temp = heap.get(i);
        heap.set(i, heap.get(j));
        heap.set(j, temp);
    }
    
    public boolean isEmpty() {
        return heap.isEmpty();
    }
    
    public int size() {
        return heap.size();
    }
}
```

### 1. Introduction to Priority Queue
```java
import java.util.*;

public class IntroToPriorityQueue {
    public static void demonstrateMinHeap() {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(3);
        minHeap.offer(1);
        minHeap.offer(4);
        minHeap.offer(2);
        
        while (!minHeap.isEmpty()) {
            System.out.println(minHeap.poll());
        }
    }
    
    public static void demonstrateMaxHeap() {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        maxHeap.offer(3);
        maxHeap.offer(1);
        maxHeap.offer(4);
        maxHeap.offer(2);
        
        while (!maxHeap.isEmpty()) {
            System.out.println(maxHeap.poll());
        }
    }
    
    public static void customComparator() {
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> Integer.compare(a[1], b[1]));
        pq.offer(new int[]{1, 5});
        pq.offer(new int[]{2, 3});
        pq.offer(new int[]{3, 8});
        
        while (!pq.isEmpty()) {
            int[] arr = pq.poll();
            System.out.println(arr[0] + " " + arr[1]);
        }
    }
}
```

### 2. Min Heap and Max Heap Implementation
```java
public class HeapImplementation {
    public static void buildMinHeap(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) {
            minHeapify(arr, n, i);
        }
    }
    
    private static void minHeapify(int[] arr, int n, int i) {
        int smallest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;
        
        if (left < n && arr[left] < arr[smallest]) {
            smallest = left;
        }
        if (right < n && arr[right] < arr[smallest]) {
            smallest = right;
        }
        
        if (smallest != i) {
            swap(arr, i, smallest);
            minHeapify(arr, n, smallest);
        }
    }
    
    public static void buildMaxHeap(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) {
            maxHeapify(arr, n, i);
        }
    }
    
    private static void maxHeapify(int[] arr, int n, int i) {
        int largest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;
        
        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }
        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }
        
        if (largest != i) {
            swap(arr, i, largest);
            maxHeapify(arr, n, largest);
        }
    }
    
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
    
    public static boolean isMinHeap(int[] arr) {
        int n = arr.length;
        for (int i = 0; i <= (n - 2) / 2; i++) {
            if (2 * i + 1 < n && arr[i] > arr[2 * i + 1]) return false;
            if (2 * i + 2 < n && arr[i] > arr[2 * i + 2]) return false;
        }
        return true;
    }
    
    public static boolean isMaxHeap(int[] arr) {
        int n = arr.length;
        for (int i = 0; i <= (n - 2) / 2; i++) {
            if (2 * i + 1 < n && arr[i] < arr[2 * i + 1]) return false;
            if (2 * i + 2 < n && arr[i] < arr[2 * i + 2]) return false;
        }
        return true;
    }
}
```

### 3. Convert Min Heap to Max Heap
```java
public class ConvertMinToMaxHeap {
    public static void convertMinToMaxHeap(int[] arr) {
        int n = arr.length;
        for (int i = (n - 2) / 2; i >= 0; i--) {
            maxHeapify(arr, n, i);
        }
    }
    
    private static void maxHeapify(int[] arr, int n, int i) {
        int largest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;
        
        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }
        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }
        
        if (largest != i) {
            swap(arr, i, largest);
            maxHeapify(arr, n, largest);
        }
    }
    
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
    
    public static void convertMaxToMinHeap(int[] arr) {
        int n = arr.length;
        for (int i = (n - 2) / 2; i >= 0; i--) {
            minHeapify(arr, n, i);
        }
    }
    
    private static void minHeapify(int[] arr, int n, int i) {
        int smallest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;
        
        if (left < n && arr[left] < arr[smallest]) {
            smallest = left;
        }
        if (right < n && arr[right] < arr[smallest]) {
            smallest = right;
        }
        
        if (smallest != i) {
            swap(arr, i, smallest);
            minHeapify(arr, n, smallest);
        }
    }
}
```

### 4. K-th Largest Element in an Array
```java
import java.util.*;

public class KthLargestElement {
    public static int findKthLargest(int[] nums, int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        
        for (int num : nums) {
            minHeap.offer(num);
            if (minHeap.size() > k) {
                minHeap.poll();
            }
        }
        
        return minHeap.peek();
    }
    
    public static int findKthLargestMaxHeap(int[] nums, int k) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        
        for (int num : nums) {
            maxHeap.offer(num);
        }
        
        for (int i = 1; i < k; i++) {
            maxHeap.poll();
        }
        
        return maxHeap.poll();
    }
    
    public static int findKthLargestQuickSelect(int[] nums, int k) {
        return quickSelect(nums, 0, nums.length - 1, nums.length - k);
    }
    
    private static int quickSelect(int[] nums, int left, int right, int kIndex) {
        if (left == right) return nums[left];
        
        int pivotIndex = partition(nums, left, right);
        
        if (pivotIndex == kIndex) {
            return nums[pivotIndex];
        } else if (pivotIndex < kIndex) {
            return quickSelect(nums, pivotIndex + 1, right, kIndex);
        } else {
            return quickSelect(nums, left, pivotIndex - 1, kIndex);
        }
    }
    
    private static int partition(int[] nums, int left, int right) {
        int pivot = nums[right];
        int i = left;
        
        for (int j = left; j < right; j++) {
            if (nums[j] <= pivot) {
                swap(nums, i, j);
                i++;
            }
        }
        
        swap(nums, i, right);
        return i;
    }
    
    private static void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```

### 5. K-th Smallest Element in an Array
```java
import java.util.*;

public class KthSmallestElement {
    public static int findKthSmallest(int[] nums, int k) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        
        for (int num : nums) {
            maxHeap.offer(num);
            if (maxHeap.size() > k) {
                maxHeap.poll();
            }
        }
        
        return maxHeap.peek();
    }
    
    public static int findKthSmallestMinHeap(int[] nums, int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        
        for (int num : nums) {
            minHeap.offer(num);
        }
        
        for (int i = 1; i < k; i++) {
            minHeap.poll();
        }
        
        return minHeap.poll();
    }
    
    public static int findKthSmallestQuickSelect(int[] nums, int k) {
        return quickSelect(nums, 0, nums.length - 1, k - 1);
    }
    
    private static int quickSelect(int[] nums, int left, int right, int kIndex) {
        if (left == right) return nums[left];
        
        int pivotIndex = partition(nums, left, right);
        
        if (pivotIndex == kIndex) {
            return nums[pivotIndex];
        } else if (pivotIndex < kIndex) {
            return quickSelect(nums, pivotIndex + 1, right, kIndex);
        } else {
            return quickSelect(nums, left, pivotIndex - 1, kIndex);
        }
    }
    
    private static int partition(int[] nums, int left, int right) {
        int pivot = nums[right];
        int i = left;
        
        for (int j = left; j < right; j++) {
            if (nums[j] <= pivot) {
                swap(nums, i, j);
                i++;
            }
        }
        
        swap(nums, i, right);
        return i;
    }
    
    private static void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```

### 6. Top K Frequent Elements
```java
import java.util.*;

public class TopKFrequentElements {
    public static int[] topKFrequent(int[] nums, int k) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int num : nums) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        
        PriorityQueue<int[]> minHeap = new PriorityQueue<>((a, b) -> a[1] - b[1]);
        
        for (Map.Entry<Integer, Integer> entry : freq.entrySet()) {
            minHeap.offer(new int[]{entry.getKey(), entry.getValue()});
            if (minHeap.size() > k) {
                minHeap.poll();
            }
        }
        
        int[] result = new int[k];
        for (int i = k - 1; i >= 0; i--) {
            result[i] = minHeap.poll()[0];
        }
        
        return result;
    }
    
    public static int[] topKFrequentMaxHeap(int[] nums, int k) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int num : nums) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        
        PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) -> b[1] - a[1]);
        
        for (Map.Entry<Integer, Integer> entry : freq.entrySet()) {
            maxHeap.offer(new int[]{entry.getKey(), entry.getValue()});
        }
        
        int[] result = new int[k];
        for (int i = 0; i < k; i++) {
            result[i] = maxHeap.poll()[0];
        }
        
        return result;
    }
    
    public static int[] topKFrequentBucketSort(int[] nums, int k) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int num : nums) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        
        List<Integer>[] buckets = new List[nums.length + 1];
        for (int i = 0; i <= nums.length; i++) {
            buckets[i] = new ArrayList<>();
        }
        
        for (Map.Entry<Integer, Integer> entry : freq.entrySet()) {
            buckets[entry.getValue()].add(entry.getKey());
        }
        
        int[] result = new int[k];
        int index = 0;
        
        for (int i = buckets.length - 1; i >= 0 && index < k; i--) {
            for (int num : buckets[i]) {
                result[index++] = num;
                if (index == k) break;
            }
        }
        
        return result;
    }
}
```

### 7. Merge K Sorted Arrays
```java
import java.util.*;

public class MergeKSortedArrays {
    public static int[] mergeKArrays(int[][] arrays) {
        PriorityQueue<int[]> minHeap = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        
        for (int i = 0; i < arrays.length; i++) {
            if (arrays[i].length > 0) {
                minHeap.offer(new int[]{arrays[i][0], i, 0});
            }
        }
        
        List<Integer> result = new ArrayList<>();
        
        while (!minHeap.isEmpty()) {
            int[] current = minHeap.poll();
            int value = current[0];
            int arrayIndex = current[1];
            int elementIndex = current[2];
            
            result.add(value);
            
            if (elementIndex + 1 < arrays[arrayIndex].length) {
                minHeap.offer(new int[]{arrays[arrayIndex][elementIndex + 1], arrayIndex, elementIndex + 1});
            }
        }
        
        return result.stream().mapToInt(i -> i).toArray();
    }
    
    public static int[] mergeKArraysDivideConquer(int[][] arrays) {
        if (arrays.length == 0) return new int[0];
        
        while (arrays.length > 1) {
            List<int[]> mergedArrays = new ArrayList<>();
            
            for (int i = 0; i < arrays.length; i += 2) {
                int[] arr1 = arrays[i];
                int[] arr2 = (i + 1 < arrays.length) ? arrays[i + 1] : new int[0];
                mergedArrays.add(mergeTwoArrays(arr1, arr2));
            }
            
            arrays = mergedArrays.toArray(new int[mergedArrays.size()][]);
        }
        
        return arrays[0];
    }
    
    private static int[] mergeTwoArrays(int[] arr1, int[] arr2) {
        int[] merged = new int[arr1.length + arr2.length];
        int i = 0, j = 0, k = 0;
        
        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] <= arr2[j]) {
                merged[k++] = arr1[i++];
            } else {
                merged[k++] = arr2[j++];
            }
        }
        
        while (i < arr1.length) {
            merged[k++] = arr1[i++];
        }
        
        while (j < arr2.length) {
            merged[k++] = arr2[j++];
        }
        
        return merged;
    }
}
```

### 8. Replace Elements by Their Rank in the Array
```java
import java.util.*;

public class ReplaceByRank {
    public static int[] replaceByRank(int[] arr) {
        int n = arr.length;
        int[] result = new int[n];
        
        PriorityQueue<int[]> minHeap = new PriorityQueue<>((a, b) -> Integer.compare(a[0], b[0]));
        
        for (int i = 0; i < n; i++) {
            minHeap.offer(new int[]{arr[i], i});
        }
        
        int rank = 1;
        int prevValue = Integer.MIN_VALUE;
        
        while (!minHeap.isEmpty()) {
            int[] current = minHeap.poll();
            int value = current[0];
            int index = current[1];
            
            if (value != prevValue) {
                if (prevValue != Integer.MIN_VALUE) {
                    rank++;
                }
                prevValue = value;
            }
            
            result[index] = rank;
        }
        
        return result;
    }
    
    public static int[] replaceByRankSorting(int[] arr) {
        int n = arr.length;
        int[][] indexedArr = new int[n][2];
        
        for (int i = 0; i < n; i++) {
            indexedArr[i][0] = arr[i];
            indexedArr[i][1] = i;
        }
        
        Arrays.sort(indexedArr, (a, b) -> Integer.compare(a[0], b[0]));
        
        int[] result = new int[n];
        int rank = 1;
        
        for (int i = 0; i < n; i++) {
            if (i > 0 && indexedArr[i][0] != indexedArr[i - 1][0]) {
                rank = i + 1;
            }
            result[indexedArr[i][1]] = rank;
        }
        
        return result;
    }
    
    public static int[] replaceByRankHashMap(int[] arr) {
        Set<Integer> uniqueElements = new HashSet<>();
        for (int num : arr) {
            uniqueElements.add(num);
        }
        
        List<Integer> sortedUnique = new ArrayList<>(uniqueElements);
        Collections.sort(sortedUnique);
        
        Map<Integer, Integer> rankMap = new HashMap<>();
        for (int i = 0; i < sortedUnique.size(); i++) {
            rankMap.put(sortedUnique.get(i), i + 1);
        }
        
        int[] result = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            result[i] = rankMap.get(arr[i]);
        }
        
        return result;
    }
}
```

### 9. Task Scheduler
```java
import java.util.*;

public class TaskScheduler {
    public static int leastInterval(char[] tasks, int n) {
        Map<Character, Integer> freq = new HashMap<>();
        for (char task : tasks) {
            freq.put(task, freq.getOrDefault(task, 0) + 1);
        }
        
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        for (int count : freq.values()) {
            maxHeap.offer(count);
        }
        
        int time = 0;
        Queue<int[]> cooldown = new LinkedList<>();
        
        while (!maxHeap.isEmpty() || !cooldown.isEmpty()) {
            time++;
            
            if (!cooldown.isEmpty() && cooldown.peek()[1] == time) {
                maxHeap.offer(cooldown.poll()[0]);
            }
            
            if (!maxHeap.isEmpty()) {
                int count = maxHeap.poll() - 1;
                if (count > 0) {
                    cooldown.offer(new int[]{count, time + n + 1});
                }
            }
        }
        
        return time;
    }
    
    public static int leastIntervalOptimized(char[] tasks, int n) {
        int[] freq = new int[26];
        for (char task : tasks) {
            freq[task - 'A']++;
        }
        
        Arrays.sort(freq);
        int maxFreq = freq[25];
        int idleSlots = (maxFreq - 1) * n;
        
        for (int i = 24; i >= 0 && idleSlots > 0; i--) {
            idleSlots -= Math.min(freq[i], maxFreq - 1);
        }
        
        return tasks.length + Math.max(0, idleSlots);
    }
    
    public static int leastIntervalMath(char[] tasks, int n) {
        int[] freq = new int[26];
        int maxCount = 0;
        int maxFreq = 0;
        
        for (char task : tasks) {
            freq[task - 'A']++;
            maxFreq = Math.max(maxFreq, freq[task - 'A']);
        }
        
        for (int f : freq) {
            if (f == maxFreq) {
                maxCount++;
            }
        }
        
        int partCount = maxFreq - 1;
        int partLength = n - (maxCount - 1);
        int emptySlots = partCount * partLength;
        int availableTasks = tasks.length - maxFreq * maxCount;
        int idles = Math.max(0, emptySlots - availableTasks);
        
        return tasks.length + idles;
    }
}
```

### 10. Hand of Straights
```java
import java.util.*;

public class HandOfStraights {
    public static boolean isNStraightHand(int[] hand, int groupSize) {
        if (hand.length % groupSize != 0) return false;
        
        Map<Integer, Integer> count = new TreeMap<>();
        for (int card : hand) {
            count.put(card, count.getOrDefault(card, 0) + 1);
        }
        
        while (!count.isEmpty()) {
            int firstCard = count.firstKey();
            
            for (int i = 0; i < groupSize; i++) {
                int currentCard = firstCard + i;
                if (!count.containsKey(currentCard)) {
                    return false;
                }
                
                count.put(currentCard, count.get(currentCard) - 1);
                if (count.get(currentCard) == 0) {
                    count.remove(currentCard);
                }
            }
        }
        
        return true;
    }
    
    public static boolean isNStraightHandPriorityQueue(int[] hand, int groupSize) {
        if (hand.length % groupSize != 0) return false;
        
        Map<Integer, Integer> freq = new HashMap<>();
        for (int card : hand) {
            freq.put(card, freq.getOrDefault(card, 0) + 1);
        }
        
        PriorityQueue<Integer> minHeap = new PriorityQueue<>(freq.keySet());
        
        while (!minHeap.isEmpty()) {
            int firstCard = minHeap.peek();
            
            for (int i = 0; i < groupSize; i++) {
                int currentCard = firstCard + i;
                
                if (!freq.containsKey(currentCard)) {
                    return false;
                }
                
                freq.put(currentCard, freq.get(currentCard) - 1);
                
                if (freq.get(currentCard) == 0) {
                    freq.remove(currentCard);
                    minHeap.remove(currentCard);
                }
            }
        }
        
        return true;
    }
    
    public static boolean isNStraightHandArray(int[] hand, int groupSize) {
        if (hand.length % groupSize != 0) return false;
        
        Arrays.sort(hand);
        boolean[] used = new boolean[hand.length];
        
        for (int i = 0; i < hand.length; i++) {
            if (used[i]) continue;
            
            int count = 1;
            int lastCard = hand[i];
            used[i] = true;
            
            for (int j = i + 1; j < hand.length && count < groupSize; j++) {
                if (!used[j] && hand[j] == lastCard + 1) {
                    used[j] = true;
                    lastCard = hand[j];
                    count++;
                }
            }
            
            if (count != groupSize) {
                return false;
            }
        }
        
        return true;
    }
}
```

### 11. Design Twitter
```java
import java.util.*;

public class Twitter {
    private Map<Integer, Set<Integer>> following;
    private Map<Integer, List<int[]>> tweets;
    private int timestamp;
    
    public Twitter() {
        following = new HashMap<>();
        tweets = new HashMap<>();
        timestamp = 0;
    }
    
    public void postTweet(int userId, int tweetId) {
        tweets.computeIfAbsent(userId, k -> new ArrayList<>()).add(new int[]{tweetId, timestamp++});
    }
    
    public List<Integer> getNewsFeed(int userId) {
        PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) -> Integer.compare(b[1], a[1]));
        
        Set<Integer> followees = following.getOrDefault(userId, new HashSet<>());
        followees.add(userId);
        
        for (int followeeId : followees) {
            if (tweets.containsKey(followeeId)) {
                for (int[] tweet : tweets.get(followeeId)) {
                    maxHeap.offer(tweet);
                }
            }
        }
        
        List<Integer> result = new ArrayList<>();
        for (int i = 0; i < 10 && !maxHeap.isEmpty(); i++) {
            result.add(maxHeap.poll()[0]);
        }
        
        return result;
    }
    
    public void follow(int followerId, int followeeId) {
        following.computeIfAbsent(followerId, k -> new HashSet<>()).add(followeeId);
    }
    
    public void unfollow(int followerId, int followeeId) {
        Set<Integer> followees = following.get(followerId);
        if (followees != null) {
            followees.remove(followeeId);
        }
    }
}

class TwitterOptimized {
    class Tweet {
        int tweetId;
        int timestamp;
        Tweet next;
        
        Tweet(int tweetId, int timestamp) {
            this.tweetId = tweetId;
            this.timestamp = timestamp;
        }
    }
    
    private Map<Integer, Set<Integer>> following;
    private Map<Integer, Tweet> tweets;
    private int timestamp;
    
    public TwitterOptimized() {
        following = new HashMap<>();
        tweets = new HashMap<>();
        timestamp = 0;
    }
    
    public void postTweet(int userId, int tweetId) {
        Tweet tweet = new Tweet(tweetId, timestamp++);
        tweet.next = tweets.get(userId);
        tweets.put(userId, tweet);
    }
    
    public List<Integer> getNewsFeed(int userId) {
        PriorityQueue<Tweet> maxHeap = new PriorityQueue<>((a, b) -> Integer.compare(b.timestamp, a.timestamp));
        
        Set<Integer> followees = following.getOrDefault(userId, new HashSet<>());
        followees.add(userId);
        
        for (int followeeId : followees) {
            Tweet tweet = tweets.get(followeeId);
            if (tweet != null) {
                maxHeap.offer(tweet);
            }
        }
        
        List<Integer> result = new ArrayList<>();
        for (int i = 0; i < 10 && !maxHeap.isEmpty(); i++) {
            Tweet tweet = maxHeap.poll();
            result.add(tweet.tweetId);
            
            if (tweet.next != null) {
                maxHeap.offer(tweet.next);
            }
        }
        
        return result;
    }
    
    public void follow(int followerId, int followeeId) {
        following.computeIfAbsent(followerId, k -> new HashSet<>()).add(followeeId);
    }
    
    public void unfollow(int followerId, int followeeId) {
        Set<Integer> followees = following.get(followerId);
        if (followees != null) {
            followees.remove(followeeId);
        }
    }
}
```

### 12. Median from Data Stream
```java
import java.util.*;

public class MedianFinder {
    private PriorityQueue<Integer> maxHeap;
    private PriorityQueue<Integer> minHeap;
    
    public MedianFinder() {
        maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        minHeap = new PriorityQueue<>();
    }
    
    public void addNum(int num) {
        if (maxHeap.isEmpty() || num <= maxHeap.peek()) {
            maxHeap.offer(num);
        } else {
            minHeap.offer(num);
        }
        
        if (maxHeap.size() > minHeap.size() + 1) {
            minHeap.offer(maxHeap.poll());
        } else if (minHeap.size() > maxHeap.size() + 1) {
            maxHeap.offer(minHeap.poll());
        }
    }
    
    public double findMedian() {
        if (maxHeap.size() == minHeap.size()) {
            return (maxHeap.peek() + minHeap.peek()) / 2.0;
        } else {
            return maxHeap.size() > minHeap.size() ? maxHeap.peek() : minHeap.peek();
        }
    }
}

class MedianFinderOptimized {
    private List<Integer> nums;
    
    public MedianFinderOptimized() {
        nums = new ArrayList<>();
    }
    
    public void addNum(int num) {
        int left = 0, right = nums.size();
        
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (nums.get(mid) < num) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        nums.add(left, num);
    }
    
    public double findMedian() {
        int n = nums.size();
        if (n % 2 == 1) {
            return nums.get(n / 2);
        } else {
            return (nums.get(n / 2 - 1) + nums.get(n / 2)) / 2.0;
        }
    }
}
```

### 13. K Closest Points to Origin
```java
import java.util.*;

public class KClosestPointsToOrigin {
    public static int[][] kClosest(int[][] points, int k) {
        PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) -> {
            int distA = a[0] * a[0] + a[1] * a[1];
            int distB = b[0] * b[0] + b[1] * b[1];
            return Integer.compare(distB, distA);
        });
        
        for (int[] point : points) {
            maxHeap.offer(point);
            if (maxHeap.size() > k) {
                maxHeap.poll();
            }
        }
        
        int[][] result = new int[k][];
        for (int i = k - 1; i >= 0; i--) {
            result[i] = maxHeap.poll();
        }
        
        return result;
    }
    
    public static int[][] kClosestSorting(int[][] points, int k) {
        Arrays.sort(points, (a, b) -> {
            int distA = a[0] * a[0] + a[1] * a[1];
            int distB = b[0] * b[0] + b[1] * b[1];
            return Integer.compare(distA, distB);
        });
        
        return Arrays.copyOfRange(points, 0, k);
    }
    
    public static int[][] kClosestQuickSelect(int[][] points, int k) {
        quickSelect(points, 0, points.length - 1, k);
        return Arrays.copyOfRange(points, 0, k);
    }
    
    private static void quickSelect(int[][] points, int left, int right, int k) {
        if (left >= right) return;
        
        int pivotIndex = partition(points, left, right);
        
        if (pivotIndex == k) {
            return;
        } else if (pivotIndex < k) {
            quickSelect(points, pivotIndex + 1, right, k);
        } else {
            quickSelect(points, left, pivotIndex - 1, k);
        }
    }
    
    private static int partition(int[][] points, int left, int right) {
        int[] pivot = points[right];
        int pivotDist = pivot[0] * pivot[0] + pivot[1] * pivot[1];
        int i = left;
        
        for (int j = left; j < right; j++) {
            int dist = points[j][0] * points[j][0] + points[j][1] * points[j][1];
            if (dist <= pivotDist) {
                swap(points, i, j);
                i++;
            }
        }
        
        swap(points, i, right);
        return i;
    }
    
    private static void swap(int[][] points, int i, int j) {
        int[] temp = points[i];
        points[i] = points[j];
        points[j] = temp;
    }
}
```

### 14. Minimum Cost to Connect Ropes
```java
import java.util.*;

public class ConnectRopes {
    public static int minCost(int[] ropes) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        
        for (int rope : ropes) {
            minHeap.offer(rope);
        }
        
        int totalCost = 0;
        
        while (minHeap.size() > 1) {
            int first = minHeap.poll();
            int second = minHeap.poll();
            
            int cost = first + second;
            totalCost += cost;
            
            minHeap.offer(cost);
        }
        
        return totalCost;
    }
    
    public static int minCostRecursive(int[] ropes) {
        return minCostHelper(ropes, 0);
    }
    
    private static int minCostHelper(int[] ropes, int currentCost) {
        if (ropes.length <= 1) return currentCost;
        
        Arrays.sort(ropes);
        
        int newLength = ropes.length - 1;
        int[] newRopes = new int[newLength];
        
        int combinedLength = ropes[0] + ropes[1];
        newRopes[0] = combinedLength;
        
        System.arraycopy(ropes, 2, newRopes, 1, ropes.length - 2);
        
        return minCostHelper(newRopes, currentCost + combinedLength);
    }
    
    public static int minCostDP(int[] ropes) {
        Arrays.sort(ropes);
        int n = ropes.length;
        int[][] dp = new int[n][n];
        
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                dp[i][j] = Integer.MAX_VALUE;
                
                for (int k = i; k < j; k++) {
                    int cost = dp[i][k] + dp[k + 1][j] + sum(ropes, i, j);
                    dp[i][j] = Math.min(dp[i][j], cost);
                }
            }
        }
        
        return dp[0][n - 1];
    }
    
    private static int sum(int[] ropes, int i, int j) {
        int total = 0;
        for (int k = i; k <= j; k++) {
            total += ropes[k];
        }
        return total;
    }
}
```

### 15. Merge K Sorted Lists
```java
import java.util.*;

class ListNode {
    int val;
    ListNode next;
    ListNode() {}
    ListNode(int val) { this.val = val; }
    ListNode(int val, ListNode next) { this.val = val; this.next = next; }
}

public class MergeKSortedLists {
    public static ListNode mergeKLists(ListNode[] lists) {
        PriorityQueue<ListNode> minHeap = new PriorityQueue<>((a, b) -> a.val - b.val);
        
        for (ListNode list : lists) {
            if (list != null) {
                minHeap.offer(list);
            }
        }
        
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        
        while (!minHeap.isEmpty()) {
            ListNode node = minHeap.poll();
            current.next = node;
            current = current.next;
            
            if (node.next != null) {
                minHeap.offer(node.next);
            }
        }
        
        return dummy.next;
    }
    
    public static ListNode mergeKListsDivideConquer(ListNode[] lists) {
        if (lists == null || lists.length == 0) return null;
        
        while (lists.length > 1) {
            List<ListNode> mergedLists = new ArrayList<>();
            
            for (int i = 0; i < lists.length; i += 2) {
                ListNode l1 = lists[i];
                ListNode l2 = (i + 1 < lists.length) ? lists[i + 1] : null;
                mergedLists.add(mergeTwoLists(l1, l2));
            }
            
            lists = mergedLists.toArray(new ListNode[0]);
        }
        
        return lists[0];
    }
    
    private static ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        
        while (l1 != null && l2 != null) {
            if (l1.val <= l2.val) {
                current.next = l1;
                l1 = l1.next;
            } else {
                current.next = l2;
                l2 = l2.next;
            }
            current = current.next;
        }
        
        current.next = (l1 != null) ? l1 : l2;
        return dummy.next;
    }
    
    public static ListNode mergeKListsRecursive(ListNode[] lists) {
        if (lists == null || lists.length == 0) return null;
        return mergeHelper(lists, 0, lists.length - 1);
    }
    
    private static ListNode mergeHelper(ListNode[] lists, int start, int end) {
        if (start == end) return lists[start];
        
        int mid = start + (end - start) / 2;
        ListNode left = mergeHelper(lists, start, mid);
        ListNode right = mergeHelper(lists, mid + 1, end);
        
        return mergeTwoLists(left, right);
    }
}
```

---


## Greedy Algorithms

### 1. Assign Cookies
**Time:** O(n log n + m log m)  
**Space:** O(1)

```java
import java.util.*;

public class AssignCookies {
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        
        int child = 0, cookie = 0;
        
        while (child < g.length && cookie < s.length) {
            if (s[cookie] >= g[child]) {
                child++;
            }
            cookie++;
        }
        
        return child;
    }
}
```

### 2. Fractional Knapsack
**Time:** O(n log n)  
**Space:** O(1)

```java
import java.util.*;

class Item {
    int value, weight;
    Item(int value, int weight) {
        this.value = value;
        this.weight = weight;
    }
}

public class FractionalKnapsack {
    public static double fractionalKnapsack(int W, Item[] items) {
        Arrays.sort(items, (a, b) -> Double.compare((double)b.value/b.weight, (double)a.value/a.weight));
        
        double result = 0.0;
        
        for (Item item : items) {
            if (W >= item.weight) {
                result += item.value;
                W -= item.weight;
            } else {
                result += item.value * ((double) W / item.weight);
                break;
            }
        }
        
        return result;
    }
}
```

### 3. Coin Change (Greedy)
**Time:** O(n)  
**Space:** O(1)

```java
public class CoinChange {
    public static int minCoins(int[] coins, int amount) {
        int count = 0;
        
        for (int i = coins.length - 1; i >= 0; i--) {
            while (amount >= coins[i]) {
                amount -= coins[i];
                count++;
            }
        }
        
        return amount == 0 ? count : -1;
    }
    
    public static List<Integer> getCoins(int[] coins, int amount) {
        List<Integer> result = new ArrayList<>();
        
        for (int i = coins.length - 1; i >= 0; i--) {
            while (amount >= coins[i]) {
                amount -= coins[i];
                result.add(coins[i]);
            }
        }
        
        return amount == 0 ? result : new ArrayList<>();
    }
}
```

### 4. Lemonade Change
**Time:** O(n)  
**Space:** O(1)

```java
public class LemonadeChange {
    public static boolean lemonadeChange(int[] bills) {
        int five = 0, ten = 0;
        
        for (int bill : bills) {
            if (bill == 5) {
                five++;
            } else if (bill == 10) {
                if (five > 0) {
                    five--;
                    ten++;
                } else {
                    return false;
                }
            } else {
                if (ten > 0 && five > 0) {
                    ten--;
                    five--;
                } else if (five >= 3) {
                    five -= 3;
                } else {
                    return false;
                }
            }
        }
        
        return true;
    }
}
```
### 5. Jump Game
**Time:** O(n)  
**Space:** O(1)

```java
public class JumpGame {
    public static boolean canJump(int[] nums) {
        int maxReach = 0;
        
        for (int i = 0; i < nums.length; i++) {
            if (i > maxReach) return false;
            maxReach = Math.max(maxReach, i + nums[i]);
        }
        
        return true;
    }
    
    public static boolean canJumpDP(int[] nums) {
        boolean[] dp = new boolean[nums.length];
        dp[0] = true;
        
        for (int i = 1; i < nums.length; i++) {
            for (int j = 0; j < i; j++) {
                if (dp[j] && j + nums[j] >= i) {
                    dp[i] = true;
                    break;
                }
            }
        }
        
        return dp[nums.length - 1];
    }
}
```

### 6. Jump Game II
**Time:** O(n)  
**Space:** O(1)

```java
public class JumpGameII {
    public static int jump(int[] nums) {
        int jumps = 0, currentEnd = 0, farthest = 0;
        
        for (int i = 0; i < nums.length - 1; i++) {
            farthest = Math.max(farthest, i + nums[i]);
            
            if (i == currentEnd) {
                jumps++;
                currentEnd = farthest;
            }
        }
        
        return jumps;
    }
    
    public static int jumpBFS(int[] nums) {
        if (nums.length <= 1) return 0;
        
        int level = 0, currentMax = 0, nextMax = 0;
        
        for (int i = 0; i < nums.length - 1; i++) {
            nextMax = Math.max(nextMax, i + nums[i]);
            
            if (i == currentMax) {
                level++;
                currentMax = nextMax;
            }
        }
        
        return level;
    }
}
```

### 7. Minimum Platforms
**Time:** O(n log n)  
**Space:** O(1)

```java
import java.util.*;

public class MinimumPlatforms {
    public static int findPlatform(int[] arr, int[] dep) {
        Arrays.sort(arr);
        Arrays.sort(dep);
        
        int platforms = 1, result = 1;
        int i = 1, j = 0;
        
        while (i < arr.length && j < dep.length) {
            if (arr[i] <= dep[j]) {
                platforms++;
                i++;
            } else {
                platforms--;
                j++;
            }
            
            result = Math.max(result, platforms);
        }
        
        return result;
    }
    
    public static int findPlatformSweepLine(int[] arr, int[] dep) {
        int[] events = new int[2401];
        
        for (int i = 0; i < arr.length; i++) {
            events[arr[i]]++;
            events[dep[i] + 1]--;
        }
        
        int platforms = 0, maxPlatforms = 0;
        
        for (int count : events) {
            platforms += count;
            maxPlatforms = Math.max(maxPlatforms, platforms);
        }
        
        return maxPlatforms;
    }
}
```

### 8. N Meetings in One Room
**Time:** O(n log n)  
**Space:** O(n)

```java
import java.util.*;

class Meeting {
    int start, end, index;
    Meeting(int start, int end, int index) {
        this.start = start;
        this.end = end;
        this.index = index;
    }
}

public class NMeetingsInRoom {
    public static int maxMeetings(int[] start, int[] end) {
        Meeting[] meetings = new Meeting[start.length];
        for (int i = 0; i < start.length; i++) {
            meetings[i] = new Meeting(start[i], end[i], i);
        }
        
        Arrays.sort(meetings, (a, b) -> Integer.compare(a.end, b.end));
        
        int count = 1;
        int lastEnd = meetings[0].end;
        
        for (int i = 1; i < meetings.length; i++) {
            if (meetings[i].start > lastEnd) {
                count++;
                lastEnd = meetings[i].end;
            }
        }
        
        return count;
    }
    
    public static List<Integer> maxMeetingsWithIndex(int[] start, int[] end) {
        Meeting[] meetings = new Meeting[start.length];
        for (int i = 0; i < start.length; i++) {
            meetings[i] = new Meeting(start[i], end[i], i + 1);
        }
        
        Arrays.sort(meetings, (a, b) -> Integer.compare(a.end, b.end));
        
        List<Integer> result = new ArrayList<>();
        result.add(meetings[0].index);
        int lastEnd = meetings[0].end;
        
        for (int i = 1; i < meetings.length; i++) {
            if (meetings[i].start > lastEnd) {
                result.add(meetings[i].index);
                lastEnd = meetings[i].end;
            }
        }
        
        return result;
    }
}
```

### 9. Job Sequencing Problem
**Time:** O(n log n + n * m)  
**Space:** O(m)

```java
import java.util.*;

class Job {
    int id, profit, deadline;
    Job(int id, int profit, int deadline) {
        this.id = id;
        this.profit = profit;
        this.deadline = deadline;
    }
}

public class JobSequencing {
    public static int[] JobScheduling(Job[] jobs) {
        Arrays.sort(jobs, (a, b) -> Integer.compare(b.profit, a.profit));
        
        int maxDeadline = 0;
        for (Job job : jobs) {
            maxDeadline = Math.max(maxDeadline, job.deadline);
        }
        
        boolean[] slot = new boolean[maxDeadline + 1];
        int jobCount = 0, totalProfit = 0;
        
        for (Job job : jobs) {
            for (int j = job.deadline; j > 0; j--) {
                if (!slot[j]) {
                    slot[j] = true;
                    jobCount++;
                    totalProfit += job.profit;
                    break;
                }
            }
        }
        
        return new int[]{jobCount, totalProfit};
    }
    
    public static List<Integer> getJobSequence(Job[] jobs) {
        Arrays.sort(jobs, (a, b) -> Integer.compare(b.profit, a.profit));
        
        int maxDeadline = 0;
        for (Job job : jobs) {
            maxDeadline = Math.max(maxDeadline, job.deadline);
        }
        
        int[] result = new int[maxDeadline + 1];
        Arrays.fill(result, -1);
        
        for (Job job : jobs) {
            for (int j = job.deadline; j > 0; j--) {
                if (result[j] == -1) {
                    result[j] = job.id;
                    break;
                }
            }
        }
        
        List<Integer> sequence = new ArrayList<>();
        for (int i = 1; i <= maxDeadline; i++) {
            if (result[i] != -1) {
                sequence.add(result[i]);
            }
        }
        
        return sequence;
    }
}
```

### 10. Candy Distribution
**Time:** O(n)  
**Space:** O(n)

```java
import java.util.*;

public class CandyDistribution {
    public static int candy(int[] ratings) {
        int n = ratings.length;
        int[] candies = new int[n];
        Arrays.fill(candies, 1);
        
        for (int i = 1; i < n; i++) {
            if (ratings[i] > ratings[i - 1]) {
                candies[i] = candies[i - 1] + 1;
            }
        }
        
        for (int i = n - 2; i >= 0; i--) {
            if (ratings[i] > ratings[i + 1]) {
                candies[i] = Math.max(candies[i], candies[i + 1] + 1);
            }
        }
        
        int sum = 0;
        for (int candy : candies) {
            sum += candy;
        }
        
        return sum;
    }
    
    public static int candyOptimal(int[] ratings) {
        int n = ratings.length;
        int up = 0, down = 0, peak = 0;
        int candies = 1;
        
        for (int i = 1; i < n; i++) {
            if (ratings[i - 1] < ratings[i]) {
                up++;
                down = 0;
                peak = up;
                candies += 1 + up;
            } else if (ratings[i - 1] > ratings[i]) {
                up = 0;
                down++;
                candies += 1 + down - (peak >= down ? 1 : 0);
            } else {
                up = down = peak = 0;
                candies += 1;
            }
        }
        
        return candies;
    }
}
```

### 11. Shortest Job First
**Time:** O(n log n)  
**Space:** O(1)

```java
import java.util.*;

public class ShortestJobFirst {
    public static int findAverageTime(int[] bt) {
        Arrays.sort(bt);
        
        int totalTime = 0;
        int waitTime = 0;
        
        for (int i = 0; i < bt.length; i++) {
            totalTime += waitTime;
            waitTime += bt[i];
        }
        
        return totalTime / bt.length;
    }
    
    public static int[] findWaitingTime(int[] bt) {
        int n = bt.length;
        int[] wt = new int[n];
        int[] processOrder = new int[n];
        
        for (int i = 0; i < n; i++) {
            processOrder[i] = i;
        }
        
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (bt[processOrder[i]] > bt[processOrder[j]]) {
                    int temp = processOrder[i];
                    processOrder[i] = processOrder[j];
                    processOrder[j] = temp;
                }
            }
        }
        
        wt[processOrder[0]] = 0;
        
        for (int i = 1; i < n; i++) {
            wt[processOrder[i]] = wt[processOrder[i - 1]] + bt[processOrder[i - 1]];
        }
        
        return wt;
    }
}
```

### 12. Page Faults in LRU
**Time:** O(n)  
**Space:** O(capacity)

```java
import java.util.*;

public class PageFaultsLRU {
    public static int pageFaults(int[] pages, int capacity) {
        Set<Integer> memory = new HashSet<>();
        Queue<Integer> indexes = new LinkedList<>();
        int pageFaults = 0;
        
        for (int page : pages) {
            if (memory.size() < capacity) {
                if (!memory.contains(page)) {
                    memory.add(page);
                    indexes.add(page);
                    pageFaults++;
                }
            } else {
                if (!memory.contains(page)) {
                    int lru = indexes.poll();
                    memory.remove(lru);
                    memory.add(page);
                    indexes.add(page);
                    pageFaults++;
                }
            }
        }
        
        return pageFaults;
    }
    
    public static int pageFaultsLinkedHashMap(int[] pages, int capacity) {
        LinkedHashMap<Integer, Integer> memory = new LinkedHashMap<Integer, Integer>(capacity, 0.75f, true) {
            protected boolean removeEldestEntry(Map.Entry eldest) {
                return size() > capacity;
            }
        };
        
        int pageFaults = 0;
        
        for (int page : pages) {
            if (!memory.containsKey(page)) {
                memory.put(page, 1);
                pageFaults++;
            } else {
                memory.get(page);
            }
        }
        
        return pageFaults;
    }
}
```

### 13. Insert Interval
**Time:** O(n)  
**Space:** O(n)

```java
import java.util.*;

public class InsertInterval {
    public static int[][] insert(int[][] intervals, int[] newInterval) {
        List<int[]> result = new ArrayList<>();
        int i = 0;
        
        while (i < intervals.length && intervals[i][1] < newInterval[0]) {
            result.add(intervals[i]);
            i++;
        }
        
        while (i < intervals.length && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
            newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
            i++;
        }
        result.add(newInterval);
        
        while (i < intervals.length) {
            result.add(intervals[i]);
            i++;
        }
        
        return result.toArray(new int[result.size()][]);
    }
    
    public static int[][] insertBinarySearch(int[][] intervals, int[] newInterval) {
        List<int[]> result = new ArrayList<>();
        
        if (intervals.length == 0) {
            return new int[][]{newInterval};
        }
        
        boolean inserted = false;
        
        for (int[] interval : intervals) {
            if (interval[1] < newInterval[0]) {
                result.add(interval);
            } else if (interval[0] > newInterval[1]) {
                if (!inserted) {
                    result.add(newInterval);
                    inserted = true;
                }
                result.add(interval);
            } else {
                newInterval[0] = Math.min(newInterval[0], interval[0]);
                newInterval[1] = Math.max(newInterval[1], interval[1]);
            }
        }
        
        if (!inserted) {
            result.add(newInterval);
        }
        
        return result.toArray(new int[result.size()][]);
    }
}
```

### 14. Merge Intervals
**Time:** O(n log n)  
**Space:** O(n)

```java
import java.util.*;

public class MergeIntervals {
    public static int[][] merge(int[][] intervals) {
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));
        
        List<int[]> merged = new ArrayList<>();
        int[] current = intervals[0];
        merged.add(current);
        
        for (int[] interval : intervals) {
            if (current[1] >= interval[0]) {
                current[1] = Math.max(current[1], interval[1]);
            } else {
                current = interval;
                merged.add(current);
            }
        }
        
        return merged.toArray(new int[merged.size()][]);
    }
    
    public static int[][] mergeStack(int[][] intervals) {
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));
        
        Stack<int[]> stack = new Stack<>();
        
        for (int[] interval : intervals) {
            if (stack.isEmpty() || stack.peek()[1] < interval[0]) {
                stack.push(interval);
            } else {
                stack.peek()[1] = Math.max(stack.peek()[1], interval[1]);
            }
        }
        
        return stack.toArray(new int[stack.size()][]);
    }
    
    public static int[][] mergeInPlace(int[][] intervals) {
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));
        
        int index = 0;
        
        for (int i = 1; i < intervals.length; i++) {
            if (intervals[index][1] >= intervals[i][0]) {
                intervals[index][1] = Math.max(intervals[index][1], intervals[i][1]);
            } else {
                index++;
                intervals[index] = intervals[i];
            }
        }
        
        return Arrays.copyOfRange(intervals, 0, index + 1);
    }
}
```

---


## Binary Trees

### Tree Node Structure

```java
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode() {}
    TreeNode(int val) { this.val = val; }
    TreeNode(int val, TreeNode left, TreeNode right) {
        this.val = val;
        this.left = left;
        this.right = right;
    }
}
```

### 1. Inorder Traversal
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class InorderTraversal {
    public static List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        inorder(root, result);
        return result;
    }
    
    private static void inorder(TreeNode node, List<Integer> result) {
        if (node == null) return;
        inorder(node.left, result);
        result.add(node.val);
        inorder(node.right, result);
    }
    
    public static List<Integer> inorderIterative(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        Stack<TreeNode> stack = new Stack<>();
        TreeNode current = root;
        
        while (current != null || !stack.isEmpty()) {
            while (current != null) {
                stack.push(current);
                current = current.left;
            }
            current = stack.pop();
            result.add(current.val);
            current = current.right;
        }
        
        return result;
    }
}
```

### 2. Preorder Traversal
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class PreorderTraversal {
    public static List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        preorder(root, result);
        return result;
    }
    
    private static void preorder(TreeNode node, List<Integer> result) {
        if (node == null) return;
        result.add(node.val);
        preorder(node.left, result);
        preorder(node.right, result);
    }
    
    public static List<Integer> preorderIterative(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        if (root == null) return result;
        
        Stack<TreeNode> stack = new Stack<>();
        stack.push(root);
        
        while (!stack.isEmpty()) {
            TreeNode node = stack.pop();
            result.add(node.val);
            
            if (node.right != null) stack.push(node.right);
            if (node.left != null) stack.push(node.left);
        }
        
        return result;
    }
}
```

### 3. Postorder Traversal
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class PostorderTraversal {
    public static List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        postorder(root, result);
        return result;
    }
    
    private static void postorder(TreeNode node, List<Integer> result) {
        if (node == null) return;
        postorder(node.left, result);
        postorder(node.right, result);
        result.add(node.val);
    }
    
    public static List<Integer> postorderIterative(TreeNode root) {
        LinkedList<Integer> result = new LinkedList<>();
        if (root == null) return result;
        
        Stack<TreeNode> stack = new Stack<>();
        stack.push(root);
        
        while (!stack.isEmpty()) {
            TreeNode node = stack.pop();
            result.addFirst(node.val);
            
            if (node.left != null) stack.push(node.left);
            if (node.right != null) stack.push(node.right);
        }
        
        return result;
    }
}
```

### 4. Level Order Traversal
**Time:** O(n) **Space:** O(w)

```java
import java.util.*;

public class LevelOrderTraversal {
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        
        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();
            
            for (int i = 0; i < levelSize; i++) {
                TreeNode node = queue.poll();
                currentLevel.add(node.val);
                
                if (node.left != null) queue.offer(node.left);
                if (node.right != null) queue.offer(node.right);
            }
            
            result.add(currentLevel);
        }
        
        return result;
    }
    
    public static List<Integer> levelOrderFlat(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        if (root == null) return result;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        
        while (!queue.isEmpty()) {
            TreeNode node = queue.poll();
            result.add(node.val);
            
            if (node.left != null) queue.offer(node.left);
            if (node.right != null) queue.offer(node.right);
        }
        
        return result;
    }
}
```

### 5. Iterative Traversals Using Single Stack
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class IterativeTraversals {
    public static List<Integer> allTraversals(TreeNode root) {
        List<Integer> pre = new ArrayList<>();
        List<Integer> in = new ArrayList<>();
        List<Integer> post = new ArrayList<>();
        
        if (root == null) return pre;
        
        Stack<Pair> stack = new Stack<>();
        stack.push(new Pair(root, 1));
        
        while (!stack.isEmpty()) {
            Pair p = stack.pop();
            
            if (p.num == 1) {
                pre.add(p.node.val);
                p.num++;
                stack.push(p);
                
                if (p.node.left != null) {
                    stack.push(new Pair(p.node.left, 1));
                }
            } else if (p.num == 2) {
                in.add(p.node.val);
                p.num++;
                stack.push(p);
                
                if (p.node.right != null) {
                    stack.push(new Pair(p.node.right, 1));
                }
            } else {
                post.add(p.node.val);
            }
        }
        
        return pre;
    }
    
    static class Pair {
        TreeNode node;
        int num;
        
        Pair(TreeNode node, int num) {
            this.node = node;
            this.num = num;
        }
    }
}
```

### 6. Morris Traversal
**Time:** O(n) **Space:** O(1)

```java
import java.util.*;

public class MorrisTraversal {
    public static List<Integer> inorderMorris(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        TreeNode current = root;
        
        while (current != null) {
            if (current.left == null) {
                result.add(current.val);
                current = current.right;
            } else {
                TreeNode predecessor = current.left;
                while (predecessor.right != null && predecessor.right != current) {
                    predecessor = predecessor.right;
                }
                
                if (predecessor.right == null) {
                    predecessor.right = current;
                    current = current.left;
                } else {
                    predecessor.right = null;
                    result.add(current.val);
                    current = current.right;
                }
            }
        }
        
        return result;
    }
    
    public static List<Integer> preorderMorris(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        TreeNode current = root;
        
        while (current != null) {
            if (current.left == null) {
                result.add(current.val);
                current = current.right;
            } else {
                TreeNode predecessor = current.left;
                while (predecessor.right != null && predecessor.right != current) {
                    predecessor = predecessor.right;
                }
                
                if (predecessor.right == null) {
                    predecessor.right = current;
                    result.add(current.val);
                    current = current.left;
                } else {
                    predecessor.right = null;
                    current = current.right;
                }
            }
        }
        
        return result;
    }
}
```

### 7. Height of Binary Tree
**Time:** O(n) **Space:** O(h)

```java
public class HeightOfBinaryTree {
    public static int maxDepth(TreeNode root) {
        if (root == null) return 0;
        return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
    }
    
    public static int maxDepthIterative(TreeNode root) {
        if (root == null) return 0;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        int depth = 0;
        
        while (!queue.isEmpty()) {
            int size = queue.size();
            depth++;
            
            for (int i = 0; i < size; i++) {
                TreeNode node = queue.poll();
                if (node.left != null) queue.offer(node.left);
                if (node.right != null) queue.offer(node.right);
            }
        }
        
        return depth;
    }
}
```

### 8. Check for Balanced Binary Tree
**Time:** O(n) **Space:** O(h)

```java
public class BalancedBinaryTree {
    public static boolean isBalanced(TreeNode root) {
        return checkHeight(root) != -1;
    }
    
    private static int checkHeight(TreeNode node) {
        if (node == null) return 0;
        
        int leftHeight = checkHeight(node.left);
        if (leftHeight == -1) return -1;
        
        int rightHeight = checkHeight(node.right);
        if (rightHeight == -1) return -1;
        
        if (Math.abs(leftHeight - rightHeight) > 1) return -1;
        
        return Math.max(leftHeight, rightHeight) + 1;
    }
}
```

### 9. Diameter of Binary Tree
**Time:** O(n) **Space:** O(h)

```java
public class DiameterOfBinaryTree {
    private static int maxDiameter = 0;
    
    public static int diameterOfBinaryTree(TreeNode root) {
        maxDiameter = 0;
        height(root);
        return maxDiameter;
    }
    
    private static int height(TreeNode node) {
        if (node == null) return 0;
        
        int leftHeight = height(node.left);
        int rightHeight = height(node.right);
        
        maxDiameter = Math.max(maxDiameter, leftHeight + rightHeight);
        
        return Math.max(leftHeight, rightHeight) + 1;
    }
}
```

### 10. Maximum Path Sum
**Time:** O(n) **Space:** O(h)

```java
public class MaximumPathSum {
    private static int maxSum = Integer.MIN_VALUE;
    
    public static int maxPathSum(TreeNode root) {
        maxSum = Integer.MIN_VALUE;
        maxGain(root);
        return maxSum;
    }
    
    private static int maxGain(TreeNode node) {
        if (node == null) return 0;
        
        int leftGain = Math.max(maxGain(node.left), 0);
        int rightGain = Math.max(maxGain(node.right), 0);
        
        int currentPathSum = node.val + leftGain + rightGain;
        maxSum = Math.max(maxSum, currentPathSum);
        
        return node.val + Math.max(leftGain, rightGain);
    }
}
```

### 11. Same Tree
**Time:** O(min(m,n)) **Space:** O(min(m,n))

```java
public class SameTree {
    public static boolean isSameTree(TreeNode p, TreeNode q) {
        if (p == null && q == null) return true;
        if (p == null || q == null) return false;
        if (p.val != q.val) return false;
        
        return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
    }
    
    public static boolean isSameTreeIterative(TreeNode p, TreeNode q) {
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(p);
        queue.offer(q);
        
        while (!queue.isEmpty()) {
            TreeNode first = queue.poll();
            TreeNode second = queue.poll();
            
            if (first == null && second == null) continue;
            if (first == null || second == null) return false;
            if (first.val != second.val) return false;
            
            queue.offer(first.left);
            queue.offer(second.left);
            queue.offer(first.right);
            queue.offer(second.right);
        }
        
        return true;
    }
}
```

### 12. Zigzag Level Order Traversal
**Time:** O(n) **Space:** O(w)

```java
import java.util.*;

public class ZigzagTraversal {
    public static List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        boolean leftToRight = true;
        
        while (!queue.isEmpty()) {
            int size = queue.size();
            List<Integer> level = new ArrayList<>();
            
            for (int i = 0; i < size; i++) {
                TreeNode node = queue.poll();
                
                if (leftToRight) {
                    level.add(node.val);
                } else {
                    level.add(0, node.val);
                }
                
                if (node.left != null) queue.offer(node.left);
                if (node.right != null) queue.offer(node.right);
            }
            
            result.add(level);
            leftToRight = !leftToRight;
        }
        
        return result;
    }
}
```

### 13. Boundary Traversal
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class BoundaryTraversal {
    public static List<Integer> boundaryOfBinaryTree(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        if (root == null) return result;
        
        if (!isLeaf(root)) result.add(root.val);
        
        addLeftBoundary(root, result);
        addLeaves(root, result);
        addRightBoundary(root, result);
        
        return result;
    }
    
    private static boolean isLeaf(TreeNode node) {
        return node.left == null && node.right == null;
    }
    
    private static void addLeftBoundary(TreeNode node, List<Integer> result) {
        TreeNode current = node.left;
        while (current != null) {
            if (!isLeaf(current)) result.add(current.val);
            if (current.left != null) current = current.left;
            else current = current.right;
        }
    }
    
    private static void addRightBoundary(TreeNode node, List<Integer> result) {
        TreeNode current = node.right;
        List<Integer> temp = new ArrayList<>();
        
        while (current != null) {
            if (!isLeaf(current)) temp.add(current.val);
            if (current.right != null) current = current.right;
            else current = current.left;
        }
        
        for (int i = temp.size() - 1; i >= 0; i--) {
            result.add(temp.get(i));
        }
    }
    
    private static void addLeaves(TreeNode node, List<Integer> result) {
        if (isLeaf(node)) {
            result.add(node.val);
            return;
        }
        if (node.left != null) addLeaves(node.left, result);
        if (node.right != null) addLeaves(node.right, result);
    }
}
```

### 14. Vertical Order Traversal
**Time:** O(n log n) **Space:** O(n)

```java
import java.util.*;

public class VerticalOrderTraversal {
    public static List<List<Integer>> verticalTraversal(TreeNode root) {
        TreeMap<Integer, TreeMap<Integer, PriorityQueue<Integer>>> map = new TreeMap<>();
        dfs(root, 0, 0, map);
        
        List<List<Integer>> result = new ArrayList<>();
        for (TreeMap<Integer, PriorityQueue<Integer>> ys : map.values()) {
            List<Integer> column = new ArrayList<>();
            for (PriorityQueue<Integer> nodes : ys.values()) {
                while (!nodes.isEmpty()) {
                    column.add(nodes.poll());
                }
            }
            result.add(column);
        }
        
        return result;
    }
    
    private static void dfs(TreeNode node, int x, int y, 
                           TreeMap<Integer, TreeMap<Integer, PriorityQueue<Integer>>> map) {
        if (node == null) return;
        
        map.putIfAbsent(x, new TreeMap<>());
        map.get(x).putIfAbsent(y, new PriorityQueue<>());
        map.get(x).get(y).offer(node.val);
        
        dfs(node.left, x - 1, y + 1, map);
        dfs(node.right, x + 1, y + 1, map);
    }
}
```

### 15. Top View of Binary Tree
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class TopView {
    public static List<Integer> topView(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        if (root == null) return result;
        
        Map<Integer, Integer> map = new TreeMap<>();
        Queue<Pair> queue = new LinkedList<>();
        queue.offer(new Pair(root, 0));
        
        while (!queue.isEmpty()) {
            Pair pair = queue.poll();
            TreeNode node = pair.node;
            int hd = pair.hd;
            
            if (!map.containsKey(hd)) {
                map.put(hd, node.val);
            }
            
            if (node.left != null) queue.offer(new Pair(node.left, hd - 1));
            if (node.right != null) queue.offer(new Pair(node.right, hd + 1));
        }
        
        for (int value : map.values()) {
            result.add(value);
        }
        
        return result;
    }
    
    static class Pair {
        TreeNode node;
        int hd;
        
        Pair(TreeNode node, int hd) {
            this.node = node;
            this.hd = hd;
        }
    }
}
```

### 16. Bottom View of Binary Tree
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class BottomView {
    public static List<Integer> bottomView(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        if (root == null) return result;
        
        Map<Integer, Integer> map = new TreeMap<>();
        Queue<Pair> queue = new LinkedList<>();
        queue.offer(new Pair(root, 0));
        
        while (!queue.isEmpty()) {
            Pair pair = queue.poll();
            TreeNode node = pair.node;
            int hd = pair.hd;
            
            map.put(hd, node.val);
            
            if (node.left != null) queue.offer(new Pair(node.left, hd - 1));
            if (node.right != null) queue.offer(new Pair(node.right, hd + 1));
        }
        
        for (int value : map.values()) {
            result.add(value);
        }
        
        return result;
    }
    
    static class Pair {
        TreeNode node;
        int hd;
        
        Pair(TreeNode node, int hd) {
            this.node = node;
            this.hd = hd;
        }
    }
}
```

### 17. Right/Left View of Binary Tree
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class RightLeftView {
    public static List<Integer> rightSideView(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        rightView(root, result, 0);
        return result;
    }
    
    private static void rightView(TreeNode node, List<Integer> result, int level) {
        if (node == null) return;
        
        if (level == result.size()) {
            result.add(node.val);
        }
        
        rightView(node.right, result, level + 1);
        rightView(node.left, result, level + 1);
    }
    
    public static List<Integer> leftSideView(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        leftView(root, result, 0);
        return result;
    }
    
    private static void leftView(TreeNode node, List<Integer> result, int level) {
        if (node == null) return;
        
        if (level == result.size()) {
            result.add(node.val);
        }
        
        leftView(node.left, result, level + 1);
        leftView(node.right, result, level + 1);
    }
}
```

### 18. Symmetric Tree
**Time:** O(n) **Space:** O(h)

```java
public class SymmetricTree {
    public static boolean isSymmetric(TreeNode root) {
        return root == null || isSymmetricHelper(root.left, root.right);
    }
    
    private static boolean isSymmetricHelper(TreeNode left, TreeNode right) {
        if (left == null && right == null) return true;
        if (left == null || right == null) return false;
        
        return left.val == right.val && 
               isSymmetricHelper(left.left, right.right) && 
               isSymmetricHelper(left.right, right.left);
    }
    
    public static boolean isSymmetricIterative(TreeNode root) {
        if (root == null) return true;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root.left);
        queue.offer(root.right);
        
        while (!queue.isEmpty()) {
            TreeNode left = queue.poll();
            TreeNode right = queue.poll();
            
            if (left == null && right == null) continue;
            if (left == null || right == null) return false;
            if (left.val != right.val) return false;
            
            queue.offer(left.left);
            queue.offer(right.right);
            queue.offer(left.right);
            queue.offer(right.left);
        }
        
        return true;
    }
}
```

### 19. Print Root to Node Path
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class RootToNodePath {
    public static List<Integer> pathToNode(TreeNode root, int target) {
        List<Integer> path = new ArrayList<>();
        if (root == null) return path;
        
        findPath(root, target, path);
        return path;
    }
    
    private static boolean findPath(TreeNode node, int target, List<Integer> path) {
        if (node == null) return false;
        
        path.add(node.val);
        
        if (node.val == target) return true;
        
        if (findPath(node.left, target, path) || findPath(node.right, target, path)) {
            return true;
        }
        
        path.remove(path.size() - 1);
        return false;
    }
}
```

### 20. Lowest Common Ancestor
**Time:** O(n) **Space:** O(h)

```java
public class LowestCommonAncestor {
    public static TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null || root == p || root == q) return root;
        
        TreeNode left = lowestCommonAncestor(root.left, p, q);
        TreeNode right = lowestCommonAncestor(root.right, p, q);
        
        if (left != null && right != null) return root;
        return left != null ? left : right;
    }
    
    public static TreeNode lowestCommonAncestorIterative(TreeNode root, TreeNode p, TreeNode q) {
        Map<TreeNode, TreeNode> parent = new HashMap<>();
        Stack<TreeNode> stack = new Stack<>();
        
        parent.put(root, null);
        stack.push(root);
        
        while (!parent.containsKey(p) || !parent.containsKey(q)) {
            TreeNode node = stack.pop();
            
            if (node.left != null) {
                parent.put(node.left, node);
                stack.push(node.left);
            }
            if (node.right != null) {
                parent.put(node.right, node);
                stack.push(node.right);
            }
        }
        
        Set<TreeNode> ancestors = new HashSet<>();
        while (p != null) {
            ancestors.add(p);
            p = parent.get(p);
        }
        
        while (!ancestors.contains(q)) {
            q = parent.get(q);
        }
        
        return q;
    }
}
```

### 21. Maximum Width of Binary Tree
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class MaximumWidth {
    public static int widthOfBinaryTree(TreeNode root) {
        if (root == null) return 0;
        
        int maxWidth = 0;
        Queue<Pair> queue = new LinkedList<>();
        queue.offer(new Pair(root, 0));
        
        while (!queue.isEmpty()) {
            int size = queue.size();
            int minIndex = queue.peek().index;
            int first = 0, last = 0;
            
            for (int i = 0; i < size; i++) {
                Pair pair = queue.poll();
                TreeNode node = pair.node;
                int currentIndex = pair.index - minIndex;
                
                if (i == 0) first = currentIndex;
                if (i == size - 1) last = currentIndex;
                
                if (node.left != null) {
                    queue.offer(new Pair(node.left, currentIndex * 2 + 1));
                }
                if (node.right != null) {
                    queue.offer(new Pair(node.right, currentIndex * 2 + 2));
                }
            }
            
            maxWidth = Math.max(maxWidth, last - first + 1);
        }
        
        return maxWidth;
    }
    
    static class Pair {
        TreeNode node;
        int index;
        
        Pair(TreeNode node, int index) {
            this.node = node;
            this.index = index;
        }
    }
}
```

### 22. Children Sum Property
**Time:** O(n) **Space:** O(h)

```java
public class ChildrenSum {
    public static boolean isSumProperty(TreeNode root) {
        if (root == null) return true;
        if (root.left == null && root.right == null) return true;
        
        int sum = 0;
        if (root.left != null) sum += root.left.val;
        if (root.right != null) sum += root.right.val;
        
        return (sum == root.val) && 
               isSumProperty(root.left) && 
               isSumProperty(root.right);
    }
    
    public static void changeTree(TreeNode root) {
        if (root == null) return;
        
        int child = 0;
        if (root.left != null) child += root.left.val;
        if (root.right != null) child += root.right.val;
        
        if (child >= root.val) {
            root.val = child;
        } else {
            if (root.left != null) root.left.val = root.val;
            if (root.right != null) root.right.val = root.val;
        }
        
        changeTree(root.left);
        changeTree(root.right);
        
        int total = 0;
        if (root.left != null) total += root.left.val;
        if (root.right != null) total += root.right.val;
        if (root.left != null || root.right != null) root.val = total;
    }
}
```

### 23. All Nodes Distance K
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class NodesDistanceK {
    public static List<Integer> distanceK(TreeNode root, TreeNode target, int k) {
        Map<TreeNode, TreeNode> parent = new HashMap<>();
        buildParent(root, parent);
        
        Queue<TreeNode> queue = new LinkedList<>();
        Set<TreeNode> visited = new HashSet<>();
        
        queue.offer(target);
        visited.add(target);
        
        int currentDistance = 0;
        
        while (!queue.isEmpty()) {
            if (currentDistance == k) break;
            currentDistance++;
            
            int size = queue.size();
            for (int i = 0; i < size; i++) {
                TreeNode node = queue.poll();
                
                if (node.left != null && !visited.contains(node.left)) {
                    visited.add(node.left);
                    queue.offer(node.left);
                }
                if (node.right != null && !visited.contains(node.right)) {
                    visited.add(node.right);
                    queue.offer(node.right);
                }
                if (parent.get(node) != null && !visited.contains(parent.get(node))) {
                    visited.add(parent.get(node));
                    queue.offer(parent.get(node));
                }
            }
        }
        
        List<Integer> result = new ArrayList<>();
        while (!queue.isEmpty()) {
            result.add(queue.poll().val);
        }
        
        return result;
    }
    
    private static void buildParent(TreeNode root, Map<TreeNode, TreeNode> parent) {
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        
        while (!queue.isEmpty()) {
            TreeNode node = queue.poll();
            
            if (node.left != null) {
                parent.put(node.left, node);
                queue.offer(node.left);
            }
            if (node.right != null) {
                parent.put(node.right, node);
                queue.offer(node.right);
            }
        }
    }
}
```

### 24. Minimum Time to Burn Tree
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class BurnTree {
    public static int minTimeToBurn(TreeNode root, int start) {
        Map<TreeNode, TreeNode> parent = new HashMap<>();
        TreeNode target = buildParent(root, parent, start);
        
        Queue<TreeNode> queue = new LinkedList<>();
        Set<TreeNode> visited = new HashSet<>();
        
        queue.offer(target);
        visited.add(target);
        
        int time = 0;
        
        while (!queue.isEmpty()) {
            boolean flag = false;
            int size = queue.size();
            
            for (int i = 0; i < size; i++) {
                TreeNode node = queue.poll();
                
                if (node.left != null && !visited.contains(node.left)) {
                    flag = true;
                    visited.add(node.left);
                    queue.offer(node.left);
                }
                if (node.right != null && !visited.contains(node.right)) {
                    flag = true;
                    visited.add(node.right);
                    queue.offer(node.right);
                }
                if (parent.get(node) != null && !visited.contains(parent.get(node))) {
                    flag = true;
                    visited.add(parent.get(node));
                    queue.offer(parent.get(node));
                }
            }
            
            if (flag) time++;
        }
        
        return time;
    }
    
    private static TreeNode buildParent(TreeNode root, Map<TreeNode, TreeNode> parent, int start) {
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        TreeNode target = null;
        
        while (!queue.isEmpty()) {
            TreeNode node = queue.poll();
            if (node.val == start) target = node;
            
            if (node.left != null) {
                parent.put(node.left, node);
                queue.offer(node.left);
            }
            if (node.right != null) {
                parent.put(node.right, node);
                queue.offer(node.right);
            }
        }
        
        return target;
    }
}
```

### 25. Count Complete Tree Nodes
**Time:** O(log²n) **Space:** O(logn)

```java
public class CountCompleteNodes {
    public static int countNodes(TreeNode root) {
        if (root == null) return 0;
        
        int leftHeight = getLeftHeight(root);
        int rightHeight = getRightHeight(root);
        
        if (leftHeight == rightHeight) {
            return (1 << leftHeight) - 1;
        }
        
        return 1 + countNodes(root.left) + countNodes(root.right);
    }
    
    private static int getLeftHeight(TreeNode node) {
        int height = 0;
        while (node != null) {
            height++;
            node = node.left;
        }
        return height;
    }
    
    private static int getRightHeight(TreeNode node) {
        int height = 0;
        while (node != null) {
            height++;
            node = node.right;
        }
        return height;
    }
}
```

### 26. Root to Leaf Paths
**Time:** O(n) **Space:** O(h × p)

```java
import java.util.*;

public class RootToLeafPaths {
    public static List<String> binaryTreePaths(TreeNode root) {
        List<String> result = new ArrayList<>();
        if (root != null) findPaths(root, "", result);
        return result;
    }
    
    private static void findPaths(TreeNode node, String path, List<String> result) {
        if (node.left == null && node.right == null) {
            result.add(path + node.val);
            return;
        }
        
        if (node.left != null) {
            findPaths(node.left, path + node.val + "->", result);
        }
        if (node.right != null) {
            findPaths(node.right, path + node.val + "->", result);
        }
    }
}
```

### 27. Lowest Common Ancestor in Binary Tree
**Time:** O(n) **Space:** O(h)

```java
public class LCABinaryTree {
    public static TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null || root == p || root == q) return root;
        
        TreeNode left = lowestCommonAncestor(root.left, p, q);
        TreeNode right = lowestCommonAncestor(root.right, p, q);
        
        if (left == null) return right;
        if (right == null) return left;
        return root;
    }
}
```

### 28. Requirements Needed to Construct Unique Binary Tree
**Time:** O(1) **Space:** O(1)

```java
public class RequirementsUniqueTree {
    public static boolean canConstructUnique(boolean hasInorder, boolean hasPreorder, 
                                           boolean hasPostorder, boolean hasLevelorder) {
        if (hasInorder && (hasPreorder || hasPostorder || hasLevelorder)) return true;
        if (hasPreorder && hasPostorder) return true;
        return false;
    }
}
```

### 29. Construct Binary Tree from Preorder and Inorder
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class ConstructFromPreorderInorder {
    public static TreeNode buildTree(int[] preorder, int[] inorder) {
        Map<Integer, Integer> inorderMap = new HashMap<>();
        for (int i = 0; i < inorder.length; i++) {
            inorderMap.put(inorder[i], i);
        }
        
        return buildTreeHelper(preorder, 0, preorder.length - 1, 
                              inorder, 0, inorder.length - 1, inorderMap);
    }
    
    private static TreeNode buildTreeHelper(int[] preorder, int preStart, int preEnd,
                                           int[] inorder, int inStart, int inEnd,
                                           Map<Integer, Integer> inorderMap) {
        if (preStart > preEnd || inStart > inEnd) return null;
        
        TreeNode root = new TreeNode(preorder[preStart]);
        int inRoot = inorderMap.get(root.val);
        int numsLeft = inRoot - inStart;
        
        root.left = buildTreeHelper(preorder, preStart + 1, preStart + numsLeft,
                                   inorder, inStart, inRoot - 1, inorderMap);
        root.right = buildTreeHelper(preorder, preStart + numsLeft + 1, preEnd,
                                    inorder, inRoot + 1, inEnd, inorderMap);
        
        return root;
    }
}
```

### 30. Construct Binary Tree from Postorder and Inorder
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class ConstructFromPostorderInorder {
    public static TreeNode buildTree(int[] inorder, int[] postorder) {
        Map<Integer, Integer> inorderMap = new HashMap<>();
        for (int i = 0; i < inorder.length; i++) {
            inorderMap.put(inorder[i], i);
        }
        
        return buildTreeHelper(inorder, 0, inorder.length - 1,
                              postorder, 0, postorder.length - 1, inorderMap);
    }
    
    private static TreeNode buildTreeHelper(int[] inorder, int inStart, int inEnd,
                                           int[] postorder, int postStart, int postEnd,
                                           Map<Integer, Integer> inorderMap) {
        if (inStart > inEnd || postStart > postEnd) return null;
        
        TreeNode root = new TreeNode(postorder[postEnd]);
        int inRoot = inorderMap.get(root.val);
        int numsLeft = inRoot - inStart;
        
        root.left = buildTreeHelper(inorder, inStart, inRoot - 1,
                                   postorder, postStart, postStart + numsLeft - 1, inorderMap);
        root.right = buildTreeHelper(inorder, inRoot + 1, inEnd,
                                    postorder, postStart + numsLeft, postEnd - 1, inorderMap);
        
        return root;
    }
}
```

### 31. Serialize and Deserialize Binary Tree
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class SerializeDeserialize {
    public static String serialize(TreeNode root) {
        if (root == null) return "null";
        
        StringBuilder sb = new StringBuilder();
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        
        while (!queue.isEmpty()) {
            TreeNode node = queue.poll();
            if (node == null) {
                sb.append("null,");
            } else {
                sb.append(node.val).append(",");
                queue.offer(node.left);
                queue.offer(node.right);
            }
        }
        
        return sb.toString();
    }
    
    public static TreeNode deserialize(String data) {
        if (data.equals("null")) return null;
        
        String[] values = data.split(",");
        TreeNode root = new TreeNode(Integer.parseInt(values[0]));
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        
        for (int i = 1; i < values.length; i++) {
            TreeNode parent = queue.poll();
            
            if (!values[i].equals("null")) {
                TreeNode left = new TreeNode(Integer.parseInt(values[i]));
                parent.left = left;
                queue.offer(left);
            }
            
            if (++i < values.length && !values[i].equals("null")) {
                TreeNode right = new TreeNode(Integer.parseInt(values[i]));
                parent.right = right;
                queue.offer(right);
            }
        }
        
        return root;
    }
}
```

### 32. Morris Preorder Traversal
**Time:** O(n) **Space:** O(1)

```java
import java.util.*;

public class MorrisPreorder {
    public static List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        TreeNode current = root;
        
        while (current != null) {
            if (current.left == null) {
                result.add(current.val);
                current = current.right;
            } else {
                TreeNode predecessor = current.left;
                while (predecessor.right != null && predecessor.right != current) {
                    predecessor = predecessor.right;
                }
                
                if (predecessor.right == null) {
                    predecessor.right = current;
                    result.add(current.val);
                    current = current.left;
                } else {
                    predecessor.right = null;
                    current = current.right;
                }
            }
        }
        
        return result;
    }
}
```

### 33. Flatten Binary Tree to Linked List
**Time:** O(n) **Space:** O(1)

```java
public class FlattenBinaryTree {
    public static void flatten(TreeNode root) {
        TreeNode current = root;
        
        while (current != null) {
            if (current.left != null) {
                TreeNode predecessor = current.left;
                while (predecessor.right != null) {
                    predecessor = predecessor.right;
                }
                
                predecessor.right = current.right;
                current.right = current.left;
                current.left = null;
            }
            
            current = current.right;
        }
    }
    
    public static void flattenRecursive(TreeNode root) {
        if (root == null) return;
        
        flattenRecursive(root.right);
        flattenRecursive(root.left);
        
        root.right = prev;
        root.left = null;
        prev = root;
    }
    
    private static TreeNode prev = null;
}
```

### 34. Binary Tree Cameras
**Time:** O(n) **Space:** O(h)

```java
public class BinaryTreeCameras {
    private static int cameras = 0;
    
    public static int minCameraCover(TreeNode root) {
        cameras = 0;
        return (dfs(root) < 1 ? 1 : 0) + cameras;
    }
    
    private static int dfs(TreeNode node) {
        if (node == null) return 2;
        
        int left = dfs(node.left);
        int right = dfs(node.right);
        
        if (left == 0 || right == 0) {
            cameras++;
            return 1;
        }
        
        return left == 1 || right == 1 ? 2 : 0;
    }
}
```

### 35. Binary Tree Maximum Path Sum
**Time:** O(n) **Space:** O(h)

```java
public class BinaryTreeMaxPathSum {
    private static int maxSum = Integer.MIN_VALUE;
    
    public static int maxPathSum(TreeNode root) {
        maxSum = Integer.MIN_VALUE;
        maxGain(root);
        return maxSum;
    }
    
    private static int maxGain(TreeNode node) {
        if (node == null) return 0;
        
        int leftGain = Math.max(maxGain(node.left), 0);
        int rightGain = Math.max(maxGain(node.right), 0);
        
        int currentMax = node.val + leftGain + rightGain;
        maxSum = Math.max(maxSum, currentMax);
        
        return node.val + Math.max(leftGain, rightGain);
    }
}
```

### 36. Binary Tree to DLL
**Time:** O(n) **Space:** O(h)

```java
public class BinaryTreeToDLL {
    private static TreeNode prev = null;
    
    public static TreeNode bToDLL(TreeNode root) {
        if (root == null) return null;
        
        TreeNode head = bToDLL(root.left);
        if (head == null) head = root;
        
        if (prev != null) {
            prev.right = root;
            root.left = prev;
        }
        prev = root;
        
        bToDLL(root.right);
        return head;
    }
}
```

### 37. Binary Tree to Circular DLL
**Time:** O(n) **Space:** O(h)

```java
public class BinaryTreeToCircularDLL {
    public static TreeNode bTreeToClist(TreeNode root) {
        if (root == null) return null;
        
        TreeNode left = bTreeToClist(root.left);
        TreeNode right = bTreeToClist(root.right);
        
        root.left = root.right = root;
        
        return concatenate(concatenate(left, root), right);
    }
    
    private static TreeNode concatenate(TreeNode leftList, TreeNode rightList) {
        if (leftList == null) return rightList;
        if (rightList == null) return leftList;
        
        TreeNode leftLast = leftList.left;
        TreeNode rightLast = rightList.left;
        
        leftLast.right = rightList;
        rightList.left = leftLast;
        leftList.left = rightLast;
        rightLast.right = leftList;
        
        return leftList;
    }
}
```

### 38. Binary Tree from Inorder and Levelorder
**Time:** O(n²) **Space:** O(n)

```java
import java.util.*;

public class ConstructFromInorderLevelorder {
    public static TreeNode buildTree(int[] inorder, int[] levelorder) {
        if (inorder.length == 0) return null;
        
        return buildTreeHelper(inorder, levelorder);
    }
    
    private static TreeNode buildTreeHelper(int[] inorder, int[] levelorder) {
        if (inorder.length == 0) return null;
        
        TreeNode root = new TreeNode(levelorder[0]);
        if (inorder.length == 1) return root;
        
        int rootIndex = -1;
        for (int i = 0; i < inorder.length; i++) {
            if (inorder[i] == levelorder[0]) {
                rootIndex = i;
                break;
            }
        }
        
        int[] leftInorder = Arrays.copyOfRange(inorder, 0, rootIndex);
        int[] rightInorder = Arrays.copyOfRange(inorder, rootIndex + 1, inorder.length);
        
        Set<Integer> leftSet = new HashSet<>();
        for (int val : leftInorder) leftSet.add(val);
        
        List<Integer> leftLevel = new ArrayList<>();
        List<Integer> rightLevel = new ArrayList<>();
        
        for (int i = 1; i < levelorder.length; i++) {
            if (leftSet.contains(levelorder[i])) {
                leftLevel.add(levelorder[i]);
            } else {
                rightLevel.add(levelorder[i]);
            }
        }
        
        root.left = buildTreeHelper(leftInorder, leftLevel.stream().mapToInt(i -> i).toArray());
        root.right = buildTreeHelper(rightInorder, rightLevel.stream().mapToInt(i -> i).toArray());
        
        return root;
    }
}
```

### 39. Tree Isomorphism
**Time:** O(min(m,n)) **Space:** O(min(m,n))

```java
public class TreeIsomorphism {
    public static boolean isIsomorphic(TreeNode n1, TreeNode n2) {
        if (n1 == null && n2 == null) return true;
        if (n1 == null || n2 == null) return false;
        if (n1.val != n2.val) return false;
        
        return (isIsomorphic(n1.left, n2.left) && isIsomorphic(n1.right, n2.right)) ||
               (isIsomorphic(n1.left, n2.right) && isIsomorphic(n1.right, n2.left));
    }
}
```

---


## Binary Search Trees

### Tree Node Structure

```java
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode() {}
    TreeNode(int val) { this.val = val; }
    TreeNode(int val, TreeNode left, TreeNode right) {
        this.val = val;
        this.left = left;
        this.right = right;
    }
}
```


### 1. Search in BST
**Time:** O(log n) **Space:** O(1)

```java
public class SearchBST {
    public static TreeNode searchBST(TreeNode root, int val) {
        while (root != null && root.val != val) {
            root = val < root.val ? root.left : root.right;
        }
        return root;
    }
    
    public static TreeNode searchBSTRecursive(TreeNode root, int val) {
        if (root == null || root.val == val) return root;
        return val < root.val ? searchBSTRecursive(root.left, val) : searchBSTRecursive(root.right, val);
    }
    
    public static boolean searchBSTBoolean(TreeNode root, int val) {
        while (root != null) {
            if (root.val == val) return true;
            root = val < root.val ? root.left : root.right;
        }
        return false;
    }
}
```

### 2. Ceil in BST
**Time:** O(log n) **Space:** O(1)

```java
public class CeilBST {
    public static int findCeil(TreeNode root, int key) {
        int ceil = -1;
        while (root != null) {
            if (root.val == key) {
                ceil = root.val;
                return ceil;
            }
            if (key > root.val) {
                root = root.right;
            } else {
                ceil = root.val;
                root = root.left;
            }
        }
        return ceil;
    }
    
    public static int findCeilRecursive(TreeNode root, int key) {
        if (root == null) return -1;
        
        if (root.val == key) return root.val;
        
        if (root.val < key) {
            return findCeilRecursive(root.right, key);
        }
        
        int ceil = findCeilRecursive(root.left, key);
        return ceil >= key ? ceil : root.val;
    }
}
```

### 3. Floor in BST
**Time:** O(log n) **Space:** O(1)

```java
public class FloorBST {
    public static int findFloor(TreeNode root, int key) {
        int floor = -1;
        while (root != null) {
            if (root.val == key) {
                floor = root.val;
                return floor;
            }
            if (key > root.val) {
                floor = root.val;
                root = root.right;
            } else {
                root = root.left;
            }
        }
        return floor;
    }
    
    public static int findFloorRecursive(TreeNode root, int key) {
        if (root == null) return -1;
        
        if (root.val == key) return root.val;
        
        if (root.val > key) {
            return findFloorRecursive(root.left, key);
        }
        
        int floor = findFloorRecursive(root.right, key);
        return floor <= key ? floor : root.val;
    }
}
```

### 4. Insert Node in BST
**Time:** O(log n) **Space:** O(log n)

```java
public class InsertBST {
    public static TreeNode insertIntoBST(TreeNode root, int val) {
        if (root == null) return new TreeNode(val);
        
        TreeNode current = root;
        while (true) {
            if (current.val <= val) {
                if (current.right != null) current = current.right;
                else {
                    current.right = new TreeNode(val);
                    break;
                }
            } else {
                if (current.left != null) current = current.left;
                else {
                    current.left = new TreeNode(val);
                    break;
                }
            }
        }
        return root;
    }
    
    public static TreeNode insertIntoBSTRecursive(TreeNode root, int val) {
        if (root == null) return new TreeNode(val);
        
        if (val > root.val) {
            root.right = insertIntoBSTRecursive(root.right, val);
        } else {
            root.left = insertIntoBSTRecursive(root.left, val);
        }
        
        return root;
    }
}
```

### 5. Delete Node in BST
**Time:** O(log n) **Space:** O(log n)

```java
public class DeleteBST {
    public static TreeNode deleteNode(TreeNode root, int key) {
        if (root == null) return null;
        
        if (root.val == key) return helper(root);
        
        TreeNode dummy = root;
        while (root != null) {
            if (root.val > key) {
                if (root.left != null && root.left.val == key) {
                    root.left = helper(root.left);
                    break;
                } else {
                    root = root.left;
                }
            } else {
                if (root.right != null && root.right.val == key) {
                    root.right = helper(root.right);
                    break;
                } else {
                    root = root.right;
                }
            }
        }
        return dummy;
    }
    
    private static TreeNode helper(TreeNode root) {
        if (root.left == null) return root.right;
        else if (root.right == null) return root.left;
        
        TreeNode rightChild = root.right;
        TreeNode lastRight = findLastRight(root.left);
        lastRight.right = rightChild;
        return root.left;
    }
    
    private static TreeNode findLastRight(TreeNode root) {
        if (root.right == null) return root;
        return findLastRight(root.right);
    }
    
    public static TreeNode deleteNodeRecursive(TreeNode root, int key) {
        if (root == null) return root;
        
        if (key < root.val) {
            root.left = deleteNodeRecursive(root.left, key);
        } else if (key > root.val) {
            root.right = deleteNodeRecursive(root.right, key);
        } else {
            if (root.left == null) return root.right;
            if (root.right == null) return root.left;
            
            TreeNode minNode = findMin(root.right);
            root.val = minNode.val;
            root.right = deleteNodeRecursive(root.right, minNode.val);
        }
        
        return root;
    }
    
    private static TreeNode findMin(TreeNode root) {
        while (root.left != null) {
            root = root.left;
        }
        return root;
    }
}
```

### 6. Kth Smallest Element in BST
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class KthSmallestBST {
    public static int kthSmallest(TreeNode root, int k) {
        Stack<TreeNode> stack = new Stack<>();
        
        while (true) {
            while (root != null) {
                stack.push(root);
                root = root.left;
            }
            root = stack.pop();
            if (--k == 0) return root.val;
            root = root.right;
        }
    }
    
    static int count = 0;
    static int result = 0;
    
    public static int kthSmallestRecursive(TreeNode root, int k) {
        count = k;
        result = 0;
        inorder(root);
        return result;
    }
    
    private static void inorder(TreeNode node) {
        if (node == null) return;
        
        inorder(node.left);
        count--;
        if (count == 0) {
            result = node.val;
            return;
        }
        inorder(node.right);
    }
    
    public static int kthSmallestMorris(TreeNode root, int k) {
        int count = 0;
        TreeNode current = root;
        
        while (current != null) {
            if (current.left == null) {
                count++;
                if (count == k) return current.val;
                current = current.right;
            } else {
                TreeNode predecessor = current.left;
                while (predecessor.right != null && predecessor.right != current) {
                    predecessor = predecessor.right;
                }
                
                if (predecessor.right == null) {
                    predecessor.right = current;
                    current = current.left;
                } else {
                    predecessor.right = null;
                    count++;
                    if (count == k) return current.val;
                    current = current.right;
                }
            }
        }
        
        return -1;
    }
}
```

### 7. Validate BST
**Time:** O(n) **Space:** O(n)

```java
public class ValidateBST {
    public static boolean isValidBST(TreeNode root) {
        return validate(root, Long.MIN_VALUE, Long.MAX_VALUE);
    }
    
    private static boolean validate(TreeNode node, long lower, long upper) {
        if (node == null) return true;
        
        if (node.val <= lower || node.val >= upper) return false;
        
        return validate(node.right, node.val, upper) && validate(node.left, lower, node.val);
    }
    
    static TreeNode prev;
    
    public static boolean isValidBSTInorder(TreeNode root) {
        prev = null;
        return inorder(root);
    }
    
    private static boolean inorder(TreeNode node) {
        if (node == null) return true;
        
        if (!inorder(node.left)) return false;
        if (prev != null && prev.val >= node.val) return false;
        prev = node;
        return inorder(node.right);
    }
}
```

### 8. LCA in BST
**Time:** O(log n) **Space:** O(1)

```java
public class LCABST {
    public static TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        while (root != null) {
            if (root.val > p.val && root.val > q.val) {
                root = root.left;
            } else if (root.val < p.val && root.val < q.val) {
                root = root.right;
            } else {
                return root;
            }
        }
        return null;
    }
    
    public static TreeNode lowestCommonAncestorRecursive(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null) return null;
        
        int curr = root.val;
        if (curr < p.val && curr < q.val) {
            return lowestCommonAncestorRecursive(root.right, p, q);
        }
        if (curr > p.val && curr > q.val) {
            return lowestCommonAncestorRecursive(root.left, p, q);
        }
        return root;
    }
}
```

### 9. Construct BST from Preorder
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class ConstructBSTFromPreorder {
    public static TreeNode bstFromPreorder(int[] preorder) {
        return bstFromPreorder(preorder, Integer.MAX_VALUE);
    }
    
    static int i = 0;
    
    private static TreeNode bstFromPreorder(int[] preorder, int bound) {
        if (i == preorder.length || preorder[i] > bound) return null;
        
        TreeNode root = new TreeNode(preorder[i++]);
        root.left = bstFromPreorder(preorder, root.val);
        root.right = bstFromPreorder(preorder, bound);
        return root;
    }
    
    public static TreeNode bstFromPreorderStack(int[] preorder) {
        Stack<TreeNode> stack = new Stack<>();
        TreeNode root = new TreeNode(preorder[0]);
        stack.push(root);
        
        for (int i = 1; i < preorder.length; i++) {
            TreeNode temp = null;
            while (!stack.isEmpty() && preorder[i] > stack.peek().val) {
                temp = stack.pop();
            }
            
            if (temp != null) {
                temp.right = new TreeNode(preorder[i]);
                stack.push(temp.right);
            } else {
                temp = stack.peek();
                temp.left = new TreeNode(preorder[i]);
                stack.push(temp.left);
            }
        }
        
        return root;
    }
}
```

### 10. Inorder Successor in BST
**Time:** O(log n) **Space:** O(1)

```java
public class InorderSuccessor {
    public static TreeNode inorderSuccessor(TreeNode root, TreeNode p) {
        TreeNode successor = null;
        
        while (root != null) {
            if (p.val >= root.val) {
                root = root.right;
            } else {
                successor = root;
                root = root.left;
            }
        }
        
        return successor;
    }
    
    public static TreeNode inorderSuccessorRecursive(TreeNode root, TreeNode p) {
        if (root == null) return null;
        
        if (root.val <= p.val) {
            return inorderSuccessorRecursive(root.right, p);
        } else {
            TreeNode left = inorderSuccessorRecursive(root.left, p);
            return left != null ? left : root;
        }
    }
    
    public static TreeNode inorderPredecessor(TreeNode root, TreeNode p) {
        TreeNode predecessor = null;
        
        while (root != null) {
            if (p.val <= root.val) {
                root = root.left;
            } else {
                predecessor = root;
                root = root.right;
            }
        }
        
        return predecessor;
    }
}
```

### 11. BST Iterator
**Time:** O(1) amortized **Space:** O(h)

```java
import java.util.*;

public class BSTIterator {
    private Stack<TreeNode> stack = new Stack<>();
    
    public BSTIterator(TreeNode root) {
        pushAll(root);
    }
    
    public int next() {
        TreeNode tmpNode = stack.pop();
        pushAll(tmpNode.right);
        return tmpNode.val;
    }
    
    public boolean hasNext() {
        return !stack.isEmpty();
    }
    
    private void pushAll(TreeNode node) {
        for (; node != null; stack.push(node), node = node.left);
    }
}

class BSTIteratorReverse {
    private Stack<TreeNode> stack = new Stack<>();
    
    public BSTIteratorReverse(TreeNode root) {
        pushAll(root);
    }
    
    public int next() {
        TreeNode tmpNode = stack.pop();
        pushAll(tmpNode.left);
        return tmpNode.val;
    }
    
    public boolean hasNext() {
        return !stack.isEmpty();
    }
    
    private void pushAll(TreeNode node) {
        for (; node != null; stack.push(node), node = node.right);
    }
}
```

### 12. Two Sum in BST
**Time:** O(n) **Space:** O(h)

```java
import java.util.*;

public class TwoSumBST {
    public static boolean findTarget(TreeNode root, int k) {
        if (root == null) return false;
        
        BSTIterator l = new BSTIterator(root, false);
        BSTIterator r = new BSTIterator(root, true);
        
        int i = l.next();
        int j = r.next();
        
        while (i < j) {
            if (i + j == k) return true;
            else if (i + j < k) i = l.next();
            else j = r.next();
        }
        
        return false;
    }
    
    static class BSTIterator {
        private Stack<TreeNode> stack = new Stack<>();
        private boolean reverse;
        
        public BSTIterator(TreeNode root, boolean isReverse) {
            reverse = isReverse;
            pushAll(root);
        }
        
        public boolean hasNext() {
            return !stack.isEmpty();
        }
        
        public int next() {
            TreeNode tmpNode = stack.pop();
            if (!reverse) pushAll(tmpNode.right);
            else pushAll(tmpNode.left);
            return tmpNode.val;
        }
        
        private void pushAll(TreeNode node) {
            while (node != null) {
                stack.push(node);
                if (reverse) node = node.right;
                else node = node.left;
            }
        }
    }
    
    public static boolean findTargetHashSet(TreeNode root, int k) {
        Set<Integer> set = new HashSet<>();
        return find(root, k, set);
    }
    
    private static boolean find(TreeNode root, int k, Set<Integer> set) {
        if (root == null) return false;
        
        if (set.contains(k - root.val)) return true;
        
        set.add(root.val);
        
        return find(root.left, k, set) || find(root.right, k, set);
    }
}
```

### 13. Recover BST
**Time:** O(n) **Space:** O(n)

```java
public class RecoverBST {
    static TreeNode first;
    static TreeNode prev;
    static TreeNode middle;
    static TreeNode last;
    
    public static void recoverTree(TreeNode root) {
        first = middle = last = null;
        prev = new TreeNode(Integer.MIN_VALUE);
        inorder(root);
        
        if (first != null && last != null) {
            int temp = first.val;
            first.val = last.val;
            last.val = temp;
        } else if (first != null && middle != null) {
            int temp = first.val;
            first.val = middle.val;
            middle.val = temp;
        }
    }
    
    private static void inorder(TreeNode root) {
        if (root == null) return;
        
        inorder(root.left);
        
        if (prev != null && (root.val < prev.val)) {
            if (first == null) {
                first = prev;
                middle = root;
            } else {
                last = root;
            }
        }
        
        prev = root;
        inorder(root.right);
    }
    
    public static void recoverTreeMorris(TreeNode root) {
        TreeNode first = null, second = null;
        TreeNode prev = new TreeNode(Integer.MIN_VALUE);
        TreeNode current = root;
        
        while (current != null) {
            if (current.left == null) {
                if (prev.val > current.val) {
                    if (first == null) first = prev;
                    second = current;
                }
                prev = current;
                current = current.right;
            } else {
                TreeNode predecessor = current.left;
                while (predecessor.right != null && predecessor.right != current) {
                    predecessor = predecessor.right;
                }
                
                if (predecessor.right == null) {
                    predecessor.right = current;
                    current = current.left;
                } else {
                    predecessor.right = null;
                    if (prev.val > current.val) {
                        if (first == null) first = prev;
                        second = current;
                    }
                    prev = current;
                    current = current.right;
                }
            }
        }
        
        int temp = first.val;
        first.val = second.val;
        second.val = temp;
    }
}
```

### 14. Largest BST in Binary Tree
**Time:** O(n) **Space:** O(n)

```java
public class LargestBST {
    static class NodeValue {
        public int maxNode, minNode, maxSize;
        
        NodeValue(int minNode, int maxNode, int maxSize) {
            this.maxNode = maxNode;
            this.minNode = minNode;
            this.maxSize = maxSize;
        }
    }
    
    public static int largestBST(TreeNode root) {
        return largestBSTSubtree(root).maxSize;
    }
    
    private static NodeValue largestBSTSubtree(TreeNode root) {
        if (root == null) {
            return new NodeValue(Integer.MAX_VALUE, Integer.MIN_VALUE, 0);
        }
        
        NodeValue left = largestBSTSubtree(root.left);
        NodeValue right = largestBSTSubtree(root.right);
        
        if (left.maxNode < root.val && root.val < right.minNode) {
            return new NodeValue(Math.min(root.val, left.minNode), 
                               Math.max(root.val, right.maxNode), 
                               left.maxSize + right.maxSize + 1);
        }
        
        return new NodeValue(Integer.MIN_VALUE, Integer.MAX_VALUE, 
                           Math.max(left.maxSize, right.maxSize));
    }
}
```

### 15. Serialize and Deserialize BST
**Time:** O(n) **Space:** O(n)

```java
import java.util.*;

public class SerializeDeserializeBST {
    public static String serialize(TreeNode root) {
        List<String> list = new ArrayList<>();
        postorder(root, list);
        return String.join(",", list);
    }
    
    private static void postorder(TreeNode root, List<String> list) {
        if (root == null) return;
        postorder(root.left, list);
        postorder(root.right, list);
        list.add(String.valueOf(root.val));
    }
    
    public static TreeNode deserialize(String data) {
        if (data.isEmpty()) return null;
        
        Stack<Integer> stack = new Stack<>();
        for (String s : data.split(",")) {
            stack.push(Integer.parseInt(s));
        }
        
        return helper(Integer.MIN_VALUE, Integer.MAX_VALUE, stack);
    }
    
    private static TreeNode helper(int lower, int upper, Stack<Integer> stack) {
        if (stack.isEmpty()) return null;
        
        int val = stack.peek();
        if (val < lower || val > upper) return null;
        
        stack.pop();
        TreeNode root = new TreeNode(val);
        root.right = helper(val, upper, stack);
        root.left = helper(lower, val, stack);
        return root;
    }
}
```

### 16. Count Complete Tree Nodes (BST Specific)
**Time:** O(log²n) **Space:** O(logn)

```java
public class CountCompleteTreeNodes {
    public static int countNodes(TreeNode root) {
        if (root == null) return 0;
        
        int leftDepth = getDepth(root, true);
        int rightDepth = getDepth(root, false);
        
        if (leftDepth == rightDepth) {
            return (1 << leftDepth) - 1;
        } else {
            return 1 + countNodes(root.left) + countNodes(root.right);
        }
    }
    
    private static int getDepth(TreeNode root, boolean isLeft) {
        int depth = 0;
        while (root != null) {
            depth++;
            root = isLeft ? root.left : root.right;
        }
        return depth;
    }
    
    public static int countNodesIterative(TreeNode root) {
        if (root == null) return 0;
        
        int count = 0;
        Stack<TreeNode> stack = new Stack<>();
        stack.push(root);
        
        while (!stack.isEmpty()) {
            TreeNode node = stack.pop();
            count++;
            
            if (node.right != null) stack.push(node.right);
            if (node.left != null) stack.push(node.left);
        }
        
        return count;
    }
}
```

---


## Graphs

### Adjacency List
```java
import java.util.*;

public class GraphRepresentation {
    public static List<List<Integer>> createAdjList(int n, int[][] edges) {
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i <= n; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] edge : edges) {
            adj.get(edge[0]).add(edge[1]);
            adj.get(edge[1]).add(edge[0]);
        }
        
        return adj;
    }
    
    public static List<List<int[]>> createWeightedAdjList(int n, int[][] edges) {
        List<List<int[]>> adj = new ArrayList<>();
        for (int i = 0; i <= n; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] edge : edges) {
            adj.get(edge[0]).add(new int[]{edge[1], edge[2]});
            adj.get(edge[1]).add(new int[]{edge[0], edge[2]});
        }
        
        return adj;
    }
}
```

### 1. Graph and Types
**Time:** O(V + E) **Space:** O(V + E)

```java
import java.util.*;

public class GraphTypes {
    public static void printAdjacencyList(List<List<Integer>> adj) {
        for (int i = 0; i < adj.size(); i++) {
            System.out.print(i + ": ");
            for (int neighbor : adj.get(i)) {
                System.out.print(neighbor + " ");
            }
            System.out.println();
        }
    }
    
    public static boolean isDirected(int[][] edges, int n) {
        Map<String, Integer> edgeCount = new HashMap<>();
        
        for (int[] edge : edges) {
            String key1 = edge[0] + "-" + edge[1];
            String key2 = edge[1] + "-" + edge[0];
            
            edgeCount.put(key1, edgeCount.getOrDefault(key1, 0) + 1);
            
            if (edgeCount.containsKey(key2)) {
                return false;
            }
        }
        
        return true;
    }
    
    public static int countConnectedComponents(List<List<Integer>> adj) {
        int n = adj.size();
        boolean[] visited = new boolean[n];
        int components = 0;
        
        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                dfs(i, adj, visited);
                components++;
            }
        }
        
        return components;
    }
    
    private static void dfs(int node, List<List<Integer>> adj, boolean[] visited) {
        visited[node] = true;
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                dfs(neighbor, adj, visited);
            }
        }
    }
}
```

### 2. BFS Traversal
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class BFSTraversal {
    public static ArrayList<Integer> bfsOfGraph(int V, ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> bfs = new ArrayList<>();
        boolean[] visited = new boolean[V];
        Queue<Integer> queue = new LinkedList<>();
        
        queue.add(0);
        visited[0] = true;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            bfs.add(node);
            
            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.add(neighbor);
                }
            }
        }
        
        return bfs;
    }
    
    public static ArrayList<Integer> bfsMultipleComponents(int V, ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> bfs = new ArrayList<>();
        boolean[] visited = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                Queue<Integer> queue = new LinkedList<>();
                queue.add(i);
                visited[i] = true;
                
                while (!queue.isEmpty()) {
                    int node = queue.poll();
                    bfs.add(node);
                    
                    for (int neighbor : adj.get(node)) {
                        if (!visited[neighbor]) {
                            visited[neighbor] = true;
                            queue.add(neighbor);
                        }
                    }
                }
            }
        }
        
        return bfs;
    }
}
```

### 3. DFS Traversal
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class DFSTraversal {
    public static ArrayList<Integer> dfsOfGraph(int V, ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> dfs = new ArrayList<>();
        boolean[] visited = new boolean[V];
        dfsHelper(0, adj, visited, dfs);
        return dfs;
    }
    
    private static void dfsHelper(int node, ArrayList<ArrayList<Integer>> adj, boolean[] visited, ArrayList<Integer> dfs) {
        visited[node] = true;
        dfs.add(node);
        
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                dfsHelper(neighbor, adj, visited, dfs);
            }
        }
    }
    
    public static ArrayList<Integer> dfsIterative(int V, ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> dfs = new ArrayList<>();
        boolean[] visited = new boolean[V];
        Stack<Integer> stack = new Stack<>();
        
        stack.push(0);
        
        while (!stack.isEmpty()) {
            int node = stack.pop();
            
            if (!visited[node]) {
                visited[node] = true;
                dfs.add(node);
                
                for (int i = adj.get(node).size() - 1; i >= 0; i--) {
                    int neighbor = adj.get(node).get(i);
                    if (!visited[neighbor]) {
                        stack.push(neighbor);
                    }
                }
            }
        }
        
        return dfs;
    }
}
```

### 4. Number of Provinces
**Time:** O(V²) **Space:** O(V)

```java
public class NumberOfProvinces {
    public static int findCircleNum(int[][] isConnected) {
        int n = isConnected.length;
        boolean[] visited = new boolean[n];
        int provinces = 0;
        
        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                dfs(i, isConnected, visited);
                provinces++;
            }
        }
        
        return provinces;
    }
    
    private static void dfs(int city, int[][] isConnected, boolean[] visited) {
        visited[city] = true;
        
        for (int i = 0; i < isConnected.length; i++) {
            if (isConnected[city][i] == 1 && !visited[i]) {
                dfs(i, isConnected, visited);
            }
        }
    }
    
    public static int findCircleNumBFS(int[][] isConnected) {
        int n = isConnected.length;
        boolean[] visited = new boolean[n];
        int provinces = 0;
        
        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                Queue<Integer> queue = new LinkedList<>();
                queue.offer(i);
                visited[i] = true;
                
                while (!queue.isEmpty()) {
                    int city = queue.poll();
                    
                    for (int j = 0; j < n; j++) {
                        if (isConnected[city][j] == 1 && !visited[j]) {
                            visited[j] = true;
                            queue.offer(j);
                        }
                    }
                }
                
                provinces++;
            }
        }
        
        return provinces;
    }
}
```

### 5. Connected Components in 2D Grid
**Time:** O(n × m) **Space:** O(n × m)

```java
import java.util.*;

public class ConnectedComponents2D {
    public static int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0) return 0;
        
        int islands = 0;
        
        for (int i = 0; i < grid.length; i++) {
            for (int j = 0; j < grid[0].length; j++) {
                if (grid[i][j] == '1') {
                    dfs(grid, i, j);
                    islands++;
                }
            }
        }
        
        return islands;
    }
    
    private static void dfs(char[][] grid, int i, int j) {
        if (i < 0 || i >= grid.length || j < 0 || j >= grid[0].length || grid[i][j] == '0') {
            return;
        }
        
        grid[i][j] = '0';
        
        dfs(grid, i + 1, j);
        dfs(grid, i - 1, j);
        dfs(grid, i, j + 1);
        dfs(grid, i, j - 1);
    }
    
    public static int numIslandsBFS(char[][] grid) {
        if (grid == null || grid.length == 0) return 0;
        
        int islands = 0;
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        for (int i = 0; i < grid.length; i++) {
            for (int j = 0; j < grid[0].length; j++) {
                if (grid[i][j] == '1') {
                    Queue<int[]> queue = new LinkedList<>();
                    queue.offer(new int[]{i, j});
                    grid[i][j] = '0';
                    
                    while (!queue.isEmpty()) {
                        int[] current = queue.poll();
                        
                        for (int[] dir : directions) {
                            int ni = current[0] + dir[0];
                            int nj = current[1] + dir[1];
                            
                            if (ni >= 0 && ni < grid.length && nj >= 0 && nj < grid[0].length && grid[ni][nj] == '1') {
                                grid[ni][nj] = '0';
                                queue.offer(new int[]{ni, nj});
                            }
                        }
                    }
                    
                    islands++;
                }
            }
        }
        
        return islands;
    }
}
```

### 6. Rotten Oranges
**Time:** O(n × m) **Space:** O(n × m)

```java
import java.util.*;

public class RottenOranges {
    public static int orangesRotting(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        Queue<int[]> queue = new LinkedList<>();
        int fresh = 0;
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 2) {
                    queue.offer(new int[]{i, j});
                } else if (grid[i][j] == 1) {
                    fresh++;
                }
            }
        }
        
        if (fresh == 0) return 0;
        
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        int minutes = 0;
        
        while (!queue.isEmpty()) {
            int size = queue.size();
            boolean rotted = false;
            
            for (int i = 0; i < size; i++) {
                int[] current = queue.poll();
                
                for (int[] dir : directions) {
                    int ni = current[0] + dir[0];
                    int nj = current[1] + dir[1];
                    
                    if (ni >= 0 && ni < m && nj >= 0 && nj < n && grid[ni][nj] == 1) {
                        grid[ni][nj] = 2;
                        queue.offer(new int[]{ni, nj});
                        fresh--;
                        rotted = true;
                    }
                }
            }
            
            if (rotted) minutes++;
        }
        
        return fresh == 0 ? minutes : -1;
    }
}
```

### 7. Flood Fill Algorithm
**Time:** O(n × m) **Space:** O(n × m)

```java
public class FloodFill {
    public static int[][] floodFill(int[][] image, int sr, int sc, int color) {
        if (image[sr][sc] == color) return image;
        
        dfs(image, sr, sc, image[sr][sc], color);
        return image;
    }
    
    private static void dfs(int[][] image, int i, int j, int originalColor, int newColor) {
        if (i < 0 || i >= image.length || j < 0 || j >= image[0].length || image[i][j] != originalColor) {
            return;
        }
        
        image[i][j] = newColor;
        
        dfs(image, i + 1, j, originalColor, newColor);
        dfs(image, i - 1, j, originalColor, newColor);
        dfs(image, i, j + 1, originalColor, newColor);
        dfs(image, i, j - 1, originalColor, newColor);
    }
    
    public static int[][] floodFillBFS(int[][] image, int sr, int sc, int color) {
        if (image[sr][sc] == color) return image;
        
        int originalColor = image[sr][sc];
        Queue<int[]> queue = new LinkedList<>();
        queue.offer(new int[]{sr, sc});
        image[sr][sc] = color;
        
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            
            for (int[] dir : directions) {
                int ni = current[0] + dir[0];
                int nj = current[1] + dir[1];
                
                if (ni >= 0 && ni < image.length && nj >= 0 && nj < image[0].length && image[ni][nj] == originalColor) {
                    image[ni][nj] = color;
                    queue.offer(new int[]{ni, nj});
                }
            }
        }
        
        return image;
    }
}
```

### 8. 0/1 Matrix (Distance of Nearest Cell)
**Time:** O(n × m) **Space:** O(n × m)

```java
import java.util.*;

public class ZeroOneMatrix {
    public static int[][] updateMatrix(int[][] mat) {
        int m = mat.length;
        int n = mat[0].length;
        int[][] result = new int[m][n];
        Queue<int[]> queue = new LinkedList<>();
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (mat[i][j] == 0) {
                    result[i][j] = 0;
                    queue.offer(new int[]{i, j});
                } else {
                    result[i][j] = Integer.MAX_VALUE;
                }
            }
        }
        
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            
            for (int[] dir : directions) {
                int ni = current[0] + dir[0];
                int nj = current[1] + dir[1];
                
                if (ni >= 0 && ni < m && nj >= 0 && nj < n) {
                    if (result[ni][nj] > result[current[0]][current[1]] + 1) {
                        result[ni][nj] = result[current[0]][current[1]] + 1;
                        queue.offer(new int[]{ni, nj});
                    }
                }
            }
        }
        
        return result;
    }
}
```

### 9. Surrounded Regions
**Time:** O(n × m) **Space:** O(n × m)

```java
public class SurroundedRegions {
    public static void solve(char[][] board) {
        if (board == null || board.length == 0) return;
        
        int m = board.length;
        int n = board[0].length;
        
        for (int i = 0; i < m; i++) {
            if (board[i][0] == 'O') dfs(board, i, 0);
            if (board[i][n - 1] == 'O') dfs(board, i, n - 1);
        }
        
        for (int j = 0; j < n; j++) {
            if (board[0][j] == 'O') dfs(board, 0, j);
            if (board[m - 1][j] == 'O') dfs(board, m - 1, j);
        }
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (board[i][j] == 'O') {
                    board[i][j] = 'X';
                } else if (board[i][j] == '#') {
                    board[i][j] = 'O';
                }
            }
        }
    }
    
    private static void dfs(char[][] board, int i, int j) {
        if (i < 0 || i >= board.length || j < 0 || j >= board[0].length || board[i][j] != 'O') {
            return;
        }
        
        board[i][j] = '#';
        
        dfs(board, i + 1, j);
        dfs(board, i - 1, j);
        dfs(board, i, j + 1);
        dfs(board, i, j - 1);
    }
}
```

### 10. Number of Enclaves
**Time:** O(n × m) **Space:** O(n × m)

```java
public class NumberOfEnclaves {
    public static int numEnclaves(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        
        for (int i = 0; i < m; i++) {
            if (grid[i][0] == 1) dfs(grid, i, 0);
            if (grid[i][n - 1] == 1) dfs(grid, i, n - 1);
        }
        
        for (int j = 0; j < n; j++) {
            if (grid[0][j] == 1) dfs(grid, 0, j);
            if (grid[m - 1][j] == 1) dfs(grid, m - 1, j);
        }
        
        int count = 0;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 1) {
                    count++;
                }
            }
        }
        
        return count;
    }
    
    private static void dfs(int[][] grid, int i, int j) {
        if (i < 0 || i >= grid.length || j < 0 || j >= grid[0].length || grid[i][j] == 0) {
            return;
        }
        
        grid[i][j] = 0;
        
        dfs(grid, i + 1, j);
        dfs(grid, i - 1, j);
        dfs(grid, i, j + 1);
        dfs(grid, i, j - 1);
    }
}
```

### 11. Word Ladder I
**Time:** O(M² × N) **Space:** O(M × N)

```java
import java.util.*;

public class WordLadder {
    public static int ladderLength(String beginWord, String endWord, List<String> wordList) {
        Set<String> wordSet = new HashSet<>(wordList);
        if (!wordSet.contains(endWord)) return 0;
        
        Queue<String> queue = new LinkedList<>();
        queue.offer(beginWord);
        wordSet.remove(beginWord);
        
        int level = 1;
        
        while (!queue.isEmpty()) {
            int size = queue.size();
            
            for (int i = 0; i < size; i++) {
                String word = queue.poll();
                
                if (word.equals(endWord)) return level;
                
                for (int j = 0; j < word.length(); j++) {
                    char[] chars = word.toCharArray();
                    
                    for (char c = 'a'; c <= 'z'; c++) {
                        chars[j] = c;
                        String newWord = new String(chars);
                        
                        if (wordSet.contains(newWord)) {
                            queue.offer(newWord);
                            wordSet.remove(newWord);
                        }
                    }
                }
            }
            
            level++;
        }
        
        return 0;
    }
}
```

### 12. Word Ladder II
**Time:** O(M² × N) **Space:** O(M × N)

```java
import java.util.*;

public class WordLadderII {
    public static List<List<String>> findLadders(String beginWord, String endWord, List<String> wordList) {
        Set<String> wordSet = new HashSet<>(wordList);
        List<List<String>> result = new ArrayList<>();
        
        if (!wordSet.contains(endWord)) return result;
        
        Map<String, List<String>> neighbors = new HashMap<>();
        Map<String, Integer> distance = new HashMap<>();
        
        bfs(beginWord, endWord, wordSet, neighbors, distance);
        dfs(beginWord, endWord, neighbors, distance, new ArrayList<>(), result);
        
        return result;
    }
    
    private static void bfs(String beginWord, String endWord, Set<String> wordSet, 
                           Map<String, List<String>> neighbors, Map<String, Integer> distance) {
        Queue<String> queue = new LinkedList<>();
        queue.offer(beginWord);
        distance.put(beginWord, 0);
        
        while (!queue.isEmpty()) {
            String word = queue.poll();
            
            for (String neighbor : getNeighbors(word, wordSet)) {
                if (!distance.containsKey(neighbor)) {
                    distance.put(neighbor, distance.get(word) + 1);
                    queue.offer(neighbor);
                }
                
                if (distance.get(neighbor) == distance.get(word) + 1) {
                    neighbors.computeIfAbsent(word, k -> new ArrayList<>()).add(neighbor);
                }
            }
        }
    }
    
    private static List<String> getNeighbors(String word, Set<String> wordSet) {
        List<String> neighbors = new ArrayList<>();
        
        for (int i = 0; i < word.length(); i++) {
            char[] chars = word.toCharArray();
            
            for (char c = 'a'; c <= 'z'; c++) {
                chars[i] = c;
                String newWord = new String(chars);
                
                if (wordSet.contains(newWord)) {
                    neighbors.add(newWord);
                }
            }
        }
        
        return neighbors;
    }
    
    private static void dfs(String word, String endWord, Map<String, List<String>> neighbors,
                           Map<String, Integer> distance, List<String> path, List<List<String>> result) {
        path.add(word);
        
        if (word.equals(endWord)) {
            result.add(new ArrayList<>(path));
        } else {
            for (String neighbor : neighbors.getOrDefault(word, new ArrayList<>())) {
                dfs(neighbor, endWord, neighbors, distance, path, result);
            }
        }
        
        path.remove(path.size() - 1);
    }
}
```

### 13. Number of Distinct Islands
**Time:** O(n × m) **Space:** O(n × m)

```java
import java.util.*;

public class NumberOfDistinctIslands {
    public static int numDistinctIslands(int[][] grid) {
        if (grid == null || grid.length == 0) return 0;
        
        int m = grid.length;
        int n = grid[0].length;
        Set<String> uniqueIslands = new HashSet<>();
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 1) {
                    StringBuilder island = new StringBuilder();
                    dfs(grid, i, j, i, j, island);
                    uniqueIslands.add(island.toString());
                }
            }
        }
        
        return uniqueIslands.size();
    }
    
    private static void dfs(int[][] grid, int i, int j, int baseI, int baseJ, StringBuilder island) {
        if (i < 0 || i >= grid.length || j < 0 || j >= grid[0].length || grid[i][j] == 0) {
            return;
        }
        
        grid[i][j] = 0;
        island.append((i - baseI) + "," + (j - baseJ) + ";");
        
        dfs(grid, i + 1, j, baseI, baseJ, island);
        dfs(grid, i - 1, j, baseI, baseJ, island);
        dfs(grid, i, j + 1, baseI, baseJ, island);
        dfs(grid, i, j - 1, baseI, baseJ, island);
    }
}
```

### 14. Bipartite Graph (BFS)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class BipartiteGraph {
    public static boolean isBipartite(int[][] graph) {
        int n = graph.length;
        int[] color = new int[n];
        Arrays.fill(color, -1);
        
        for (int i = 0; i < n; i++) {
            if (color[i] == -1) {
                if (!bfsCheck(graph, i, color)) {
                    return false;
                }
            }
        }
        
        return true;
    }
    
    private static boolean bfsCheck(int[][] graph, int start, int[] color) {
        Queue<Integer> queue = new LinkedList<>();
        queue.offer(start);
        color[start] = 0;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            
            for (int neighbor : graph[node]) {
                if (color[neighbor] == -1) {
                    color[neighbor] = 1 - color[node];
                    queue.offer(neighbor);
                } else if (color[neighbor] == color[node]) {
                    return false;
                }
            }
        }
        
        return true;
    }
    
    public static boolean isBipartiteDFS(int[][] graph) {
        int n = graph.length;
        int[] color = new int[n];
        Arrays.fill(color, -1);
        
        for (int i = 0; i < n; i++) {
            if (color[i] == -1) {
                if (!dfsCheck(graph, i, 0, color)) {
                    return false;
                }
            }
        }
        
        return true;
    }
    
    private static boolean dfsCheck(int[][] graph, int node, int col, int[] color) {
        color[node] = col;
        
        for (int neighbor : graph[node]) {
            if (color[neighbor] == -1) {
                if (!dfsCheck(graph, neighbor, 1 - col, color)) {
                    return false;
                }
            } else if (color[neighbor] == col) {
                return false;
            }
        }
        
        return true;
    }
}
```

### 15. Detect Cycle in Undirected Graph (DFS)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class DetectCycleUndirected {
    public static boolean isCycle(int V, ArrayList<ArrayList<Integer>> adj) {
        boolean[] visited = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                if (dfs(i, -1, adj, visited)) {
                    return true;
                }
            }
        }
        
        return false;
    }
    
    private static boolean dfs(int node, int parent, ArrayList<ArrayList<Integer>> adj, boolean[] visited) {
        visited[node] = true;
        
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                if (dfs(neighbor, node, adj, visited)) {
                    return true;
                }
            } else if (neighbor != parent) {
                return true;
            }
        }
        
        return false;
    }
    
    public static boolean isCycleBFS(int V, ArrayList<ArrayList<Integer>> adj) {
        boolean[] visited = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                if (bfsCheck(i, adj, visited)) {
                    return true;
                }
            }
        }
        
        return false;
    }
    
    private static boolean bfsCheck(int start, ArrayList<ArrayList<Integer>> adj, boolean[] visited) {
        Queue<int[]> queue = new LinkedList<>();
        queue.offer(new int[]{start, -1});
        visited[start] = true;
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int node = current[0];
            int parent = current[1];
            
            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(new int[]{neighbor, node});
                } else if (neighbor != parent) {
                    return true;
                }
            }
        }
        
        return false;
    }
}
```

### 16. Detect Cycle in Directed Graph (DFS)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class DetectCycleDirected {
    public static boolean isCyclic(int V, ArrayList<ArrayList<Integer>> adj) {
        boolean[] visited = new boolean[V];
        boolean[] recStack = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                if (dfs(i, adj, visited, recStack)) {
                    return true;
                }
            }
        }
        
        return false;
    }
    
    private static boolean dfs(int node, ArrayList<ArrayList<Integer>> adj, boolean[] visited, boolean[] recStack) {
        visited[node] = true;
        recStack[node] = true;
        
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                if (dfs(neighbor, adj, visited, recStack)) {
                    return true;
                }
            } else if (recStack[neighbor]) {
                return true;
            }
        }
        
        recStack[node] = false;
        return false;
    }
    
    public static boolean isCyclicKahn(int V, ArrayList<ArrayList<Integer>> adj) {
        int[] indegree = new int[V];
        
        for (int i = 0; i < V; i++) {
            for (int neighbor : adj.get(i)) {
                indegree[neighbor]++;
            }
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < V; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        int count = 0;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            count++;
            
            for (int neighbor : adj.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return count != V;
    }
}
```

### 17. Safe States in Graph
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class SafeStates {
    public static List<Integer> eventualSafeNodes(int[][] graph) {
        int n = graph.length;
        int[] color = new int[n];
        List<Integer> result = new ArrayList<>();
        
        for (int i = 0; i < n; i++) {
            if (dfs(i, graph, color)) {
                result.add(i);
            }
        }
        
        return result;
    }
    
    private static boolean dfs(int node, int[][] graph, int[] color) {
        if (color[node] != 0) {
            return color[node] == 2;
        }
        
        color[node] = 1;
        
        for (int neighbor : graph[node]) {
            if (!dfs(neighbor, graph, color)) {
                return false;
            }
        }
        
        color[node] = 2;
        return true;
    }
    
    public static List<Integer> eventualSafeNodesKahn(int[][] graph) {
        int n = graph.length;
        List<List<Integer>> reverseGraph = new ArrayList<>();
        int[] indegree = new int[n];
        
        for (int i = 0; i < n; i++) {
            reverseGraph.add(new ArrayList<>());
        }
        
        for (int i = 0; i < n; i++) {
            for (int neighbor : graph[i]) {
                reverseGraph.get(neighbor).add(i);
                indegree[i]++;
            }
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < n; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        boolean[] safe = new boolean[n];
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            safe[node] = true;
            
            for (int neighbor : reverseGraph.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        List<Integer> result = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            if (safe[i]) {
                result.add(i);
            }
        }
        
        return result;
    }
}
```

### 18. Course Schedule

```java
// Course Schedule
public class CourseSchedule {
    public static boolean canFinish(int numCourses, int[][] prerequisites) {
        List<List<Integer>> adj = new ArrayList<>();
        int[] indegree = new int[numCourses];
        
        for (int i = 0; i < numCourses; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] prereq : prerequisites) {
            adj.get(prereq[1]).add(prereq[0]);
            indegree[prereq[0]]++;
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < numCourses; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        int count = 0;
        while (!queue.isEmpty()) {
            int node = queue.poll();
            count++;
            
            for (int neighbor : adj.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return count == numCourses;
    }
}

// Course Schedule II
public class CourseScheduleII {
    public static int[] findOrder(int numCourses, int[][] prerequisites) {
        List<List<Integer>> adj = new ArrayList<>();
        int[] indegree = new int[numCourses];
        
        for (int i = 0; i < numCourses; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] prereq : prerequisites) {
            adj.get(prereq[1]).add(prereq[0]);
            indegree[prereq[0]]++;
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < numCourses; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        int[] result = new int[numCourses];
        int index = 0;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            result[index++] = node;
            
            for (int neighbor : adj.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return index == numCourses ? result : new int[0];
    }
}
```

### 19. Topological Sort (DFS)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class TopologicalSort {
    public static int[] topoSort(int V, ArrayList<ArrayList<Integer>> adj) {
        boolean[] visited = new boolean[V];
        Stack<Integer> stack = new Stack<>();
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                dfs(i, adj, visited, stack);
            }
        }
        
        int[] result = new int[V];
        int index = 0;
        
        while (!stack.isEmpty()) {
            result[index++] = stack.pop();
        }
        
        return result;
    }
    
    private static void dfs(int node, ArrayList<ArrayList<Integer>> adj, boolean[] visited, Stack<Integer> stack) {
        visited[node] = true;
        
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                dfs(neighbor, adj, visited, stack);
            }
        }
        
        stack.push(node);
    }
}
```

### 20. Topological Sort (BFS/Kahn's Algorithm)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class TopologicalSortKahn {
    public static int[] topoSort(int V, ArrayList<ArrayList<Integer>> adj) {
        int[] indegree = new int[V];
        
        for (int i = 0; i < V; i++) {
            for (int neighbor : adj.get(i)) {
                indegree[neighbor]++;
            }
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < V; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        int[] result = new int[V];
        int index = 0;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            result[index++] = node;
            
            for (int neighbor : adj.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return result;
    }
}
```

### 21. Detect Cycle in Directed Graph (DFS)
**Time:** O(V + E) **Space:** O(V)

```java
public class CycleDetectionDirectedDFS {
    public static boolean isCyclic(int V, ArrayList<ArrayList<Integer>> adj) {
        boolean[] visited = new boolean[V];
        boolean[] recStack = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                if (dfs(i, adj, visited, recStack)) {
                    return true;
                }
            }
        }
        
        return false;
    }
    
    private static boolean dfs(int node, ArrayList<ArrayList<Integer>> adj, boolean[] visited, boolean[] recStack) {
        visited[node] = true;
        recStack[node] = true;
        
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                if (dfs(neighbor, adj, visited, recStack)) {
                    return true;
                }
            } else if (recStack[neighbor]) {
                return true;
            }
        }
        
        recStack[node] = false;
        return false;
    }
}
```

### 22. Course Schedule and Variants
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class CourseScheduleVariants {
    public static boolean canFinish(int numCourses, int[][] prerequisites) {
        List<List<Integer>> adj = new ArrayList<>();
        int[] indegree = new int[numCourses];
        
        for (int i = 0; i < numCourses; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] prereq : prerequisites) {
            adj.get(prereq[1]).add(prereq[0]);
            indegree[prereq[0]]++;
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < numCourses; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        int count = 0;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            count++;
            
            for (int neighbor : adj.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return count == numCourses;
    }
    
    public static int[] findOrder(int numCourses, int[][] prerequisites) {
        List<List<Integer>> adj = new ArrayList<>();
        int[] indegree = new int[numCourses];
        
        for (int i = 0; i < numCourses; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] prereq : prerequisites) {
            adj.get(prereq[1]).add(prereq[0]);
            indegree[prereq[0]]++;
        }
        
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < numCourses; i++) {
            if (indegree[i] == 0) {
                queue.offer(i);
            }
        }
        
        int[] result = new int[numCourses];
        int index = 0;
        
        while (!queue.isEmpty()) {
            int node = queue.poll();
            result[index++] = node;
            
            for (int neighbor : adj.get(node)) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return index == numCourses ? result : new int[0];
    }
}
```

### 23. Shortest Path in Binary Matrix
**Time:** O(n²) **Space:** O(n²)

```java
import java.util.*;

public class ShortestPathBinaryMatrix {
    public static int shortestPathBinaryMatrix(int[][] grid) {
        if (grid[0][0] == 1) return -1;
        
        int n = grid.length;
        if (n == 1) return 1;
        
        Queue<int[]> queue = new LinkedList<>();
        boolean[][] visited = new boolean[n][n];
        
        queue.offer(new int[]{0, 0, 1});
        visited[0][0] = true;
        
        int[][] directions = {{-1, -1}, {-1, 0}, {-1, 1}, {0, -1}, {0, 1}, {1, -1}, {1, 0}, {1, 1}};
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int row = current[0];
            int col = current[1];
            int dist = current[2];
            
            for (int[] dir : directions) {
                int newRow = row + dir[0];
                int newCol = col + dir[1];
                
                if (newRow >= 0 && newRow < n && newCol >= 0 && newCol < n && 
                    grid[newRow][newCol] == 0 && !visited[newRow][newCol]) {
                    
                    if (newRow == n - 1 && newCol == n - 1) {
                        return dist + 1;
                    }
                    
                    visited[newRow][newCol] = true;
                    queue.offer(new int[]{newRow, newCol, dist + 1});
                }
            }
        }
        
        return -1;
    }
}
```

### 24. Dijkstra Algorithm
**Time:** O((V + E) log V) **Space:** O(V)

```java
import java.util.*;

public class DijkstraAlgorithm {
    public static int[] dijkstra(int V, ArrayList<ArrayList<ArrayList<Integer>>> adj, int S) {
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        int[] dist = new int[V];
        Arrays.fill(dist, Integer.MAX_VALUE);
        
        dist[S] = 0;
        pq.offer(new int[]{0, S});
        
        while (!pq.isEmpty()) {
            int[] current = pq.poll();
            int d = current[0];
            int u = current[1];
            
            if (d > dist[u]) continue;
            
            for (ArrayList<Integer> edge : adj.get(u)) {
                int v = edge.get(0);
                int weight = edge.get(1);
                
                if (dist[u] + weight < dist[v]) {
                    dist[v] = dist[u] + weight;
                    pq.offer(new int[]{dist[v], v});
                }
            }
        }
        
        return dist;
    }
    
    public static int[] dijkstraSet(int V, ArrayList<ArrayList<ArrayList<Integer>>> adj, int S) {
        TreeSet<int[]> set = new TreeSet<>((a, b) -> a[0] == b[0] ? a[1] - b[1] : a[0] - b[0]);
        int[] dist = new int[V];
        Arrays.fill(dist, Integer.MAX_VALUE);
        
        dist[S] = 0;
        set.add(new int[]{0, S});
        
        while (!set.isEmpty()) {
            int[] current = set.pollFirst();
            int d = current[0];
            int u = current[1];
            
            for (ArrayList<Integer> edge : adj.get(u)) {
                int v = edge.get(0);
                int weight = edge.get(1);
                
                if (dist[u] + weight < dist[v]) {
                    if (dist[v] != Integer.MAX_VALUE) {
                        set.remove(new int[]{dist[v], v});
                    }
                    
                    dist[v] = dist[u] + weight;
                    set.add(new int[]{dist[v], v});
                }
            }
        }
        
        return dist;
    }
}
```

### 25. Bellman Ford Algorithm
**Time:** O(V × E) **Space:** O(V)

```java
import java.util.*;

public class BellmanFord {
    public static int[] bellmanFord(int V, ArrayList<ArrayList<Integer>> edges, int S) {
        int[] dist = new int[V];
        Arrays.fill(dist, 100000000);
        dist[S] = 0;
        
        for (int i = 0; i < V - 1; i++) {
            for (ArrayList<Integer> edge : edges) {
                int u = edge.get(0);
                int v = edge.get(1);
                int weight = edge.get(2);
                
                if (dist[u] != 100000000 && dist[u] + weight < dist[v]) {
                    dist[v] = dist[u] + weight;
                }
            }
        }
        
        for (ArrayList<Integer> edge : edges) {
            int u = edge.get(0);
            int v = edge.get(1);
            int weight = edge.get(2);
            
            if (dist[u] != 100000000 && dist[u] + weight < dist[v]) {
                return new int[]{-1};
            }
        }
        
        return dist;
    }
}
```

### 26. Floyd Warshall Algorithm
**Time:** O(V³) **Space:** O(V²)

```java
public class FloydWarshall {
    public static void shortest_distance(int[][] matrix) {
        int n = matrix.length;
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (matrix[i][j] == -1) {
                    matrix[i][j] = 1000000;
                }
                if (i == j) {
                    matrix[i][j] = 0;
                }
            }
        }
        
        for (int k = 0; k < n; k++) {
            for (int i = 0; i < n; i++) {
                for (int j = 0; j < n; j++) {
                    matrix[i][j] = Math.min(matrix[i][j], matrix[i][k] + matrix[k][j]);
                }
            }
        }
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (matrix[i][j] == 1000000) {
                    matrix[i][j] = -1;
                }
            }
        }
    }
}
```

### 27. Find the City With the Smallest Number of Neighbors at a Threshold Distance
**Time:** O(V³) **Space:** O(V²)

```java
public class FindTheCity {
    public static int findTheCity(int n, int[][] edges, int distanceThreshold) {
        int[][] dist = new int[n][n];
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i == j) {
                    dist[i][j] = 0;
                } else {
                    dist[i][j] = 1000000;
                }
            }
        }
        
        for (int[] edge : edges) {
            dist[edge[0]][edge[1]] = edge[2];
            dist[edge[1]][edge[0]] = edge[2];
        }
        
        for (int k = 0; k < n; k++) {
            for (int i = 0; i < n; i++) {
                for (int j = 0; j < n; j++) {
                    if (dist[i][k] + dist[k][j] < dist[i][j]) {
                        dist[i][j] = dist[i][k] + dist[k][j];
                    }
                }
            }
        }
        
        int city = -1;
        int minCount = n;
        
        for (int i = 0; i < n; i++) {
            int count = 0;
            for (int j = 0; j < n; j++) {
                if (dist[i][j] <= distanceThreshold) {
                    count++;
                }
            }
            
            if (count <= minCount) {
                minCount = count;
                city = i;
            }
        }
        
        return city;
    }
}
```

### 28. Minimum Multiplications to Reach End
**Time:** O(100000 × N) **Space:** O(100000)

```java
import java.util.*;

public class MinimumMultiplications {
    public static int minimumMultiplications(int[] arr, int start, int end) {
        if (start == end) return 0;
        
        Queue<int[]> queue = new LinkedList<>();
        int[] dist = new int[100000];
        Arrays.fill(dist, Integer.MAX_VALUE);
        
        dist[start] = 0;
        queue.offer(new int[]{start, 0});
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int node = current[0];
            int steps = current[1];
            
            for (int num : arr) {
                int next = (node * num) % 100000;
                
                if (steps + 1 < dist[next]) {
                    dist[next] = steps + 1;
                    
                    if (next == end) {
                        return steps + 1;
                    }
                    
                    queue.offer(new int[]{next, steps + 1});
                }
            }
        }
        
        return -1;
    }
}
```

### 29. Number of Ways to Arrive at Destination
**Time:** O((V + E) log V) **Space:** O(V)

```java
import java.util.*;

public class NumberOfWaysToDestination {
    public static int countPaths(int n, int[][] roads) {
        int MOD = 1000000007;
        List<List<int[]>> adj = new ArrayList<>();
        
        for (int i = 0; i < n; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] road : roads) {
            adj.get(road[0]).add(new int[]{road[1], road[2]});
            adj.get(road[1]).add(new int[]{road[0], road[2]});
        }
        
        PriorityQueue<long[]> pq = new PriorityQueue<>((a, b) -> Long.compare(a[0], b[0]));
        long[] dist = new long[n];
        long[] ways = new long[n];
        
        Arrays.fill(dist, Long.MAX_VALUE);
        dist[0] = 0;
        ways[0] = 1;
        
        pq.offer(new long[]{0, 0});
        
        while (!pq.isEmpty()) {
            long[] current = pq.poll();
            long d = current[0];
            int u = (int) current[1];
            
            if (d > dist[u]) continue;
            
            for (int[] edge : adj.get(u)) {
                int v = edge[0];
                int weight = edge[1];
                
                if (dist[u] + weight < dist[v]) {
                    dist[v] = dist[u] + weight;
                    ways[v] = ways[u];
                    pq.offer(new long[]{dist[v], v});
                } else if (dist[u] + weight == dist[v]) {
                    ways[v] = (ways[v] + ways[u]) % MOD;
                }
            }
        }
        
        return (int) ways[n - 1];
    }
}
```

### 30. Minimum Effort Path
**Time:** O(m × n × log(m × n)) **Space:** O(m × n)

```java
import java.util.*;

public class MinimumEffortPath {
    public static int minimumEffortPath(int[][] heights) {
        int m = heights.length;
        int n = heights[0].length;
        
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        int[][] dist = new int[m][n];
        
        for (int i = 0; i < m; i++) {
            Arrays.fill(dist[i], Integer.MAX_VALUE);
        }
        
        dist[0][0] = 0;
        pq.offer(new int[]{0, 0, 0});
        
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        while (!pq.isEmpty()) {
            int[] current = pq.poll();
            int effort = current[0];
            int row = current[1];
            int col = current[2];
            
            if (row == m - 1 && col == n - 1) {
                return effort;
            }
            
            if (effort > dist[row][col]) continue;
            
            for (int[] dir : directions) {
                int newRow = row + dir[0];
                int newCol = col + dir[1];
                
                if (newRow >= 0 && newRow < m && newCol >= 0 && newCol < n) {
                    int newEffort = Math.max(effort, Math.abs(heights[newRow][newCol] - heights[row][col]));
                    
                    if (newEffort < dist[newRow][newCol]) {
                        dist[newRow][newCol] = newEffort;
                        pq.offer(new int[]{newEffort, newRow, newCol});
                    }
                }
            }
        }
        
        return 0;
    }
}
```

### 31. Cheapest Flights Within K Stops
**Time:** O(E × K) **Space:** O(V)

```java
import java.util.*;

public class CheapestFlights {
    public static int findCheapestPrice(int n, int[][] flights, int src, int dst, int k) {
        int[] dist = new int[n];
        Arrays.fill(dist, Integer.MAX_VALUE);
        dist[src] = 0;
        
        for (int i = 0; i <= k; i++) {
            int[] temp = Arrays.copyOf(dist, n);
            
            for (int[] flight : flights) {
                int from = flight[0];
                int to = flight[1];
                int price = flight[2];
                
                if (dist[from] != Integer.MAX_VALUE) {
                    temp[to] = Math.min(temp[to], dist[from] + price);
                }
            }
            
            dist = temp;
        }
        
        return dist[dst] == Integer.MAX_VALUE ? -1 : dist[dst];
    }
    
    public static int findCheapestPriceDijkstra(int n, int[][] flights, int src, int dst, int k) {
        List<List<int[]>> adj = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (int[] flight : flights) {
            adj.get(flight[0]).add(new int[]{flight[1], flight[2]});
        }
        
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        pq.offer(new int[]{0, src, 0});
        
        int[] stops = new int[n];
        Arrays.fill(stops, Integer.MAX_VALUE);
        
        while (!pq.isEmpty()) {
            int[] current = pq.poll();
            int cost = current[0];
            int node = current[1];
            int stopCount = current[2];
            
            if (stopCount > stops[node] || stopCount > k + 1) continue;
            stops[node] = stopCount;
            
            if (node == dst) return cost;
            
            for (int[] edge : adj.get(node)) {
                pq.offer(new int[]{cost + edge[1], edge[0], stopCount + 1});
            }
        }
        
        return -1;
    }
}
```

### 32. Disjoint Set Union (Union by Rank and Path Compression)
**Time:** O(4α(n)) ≈ O(1) **Space:** O(n)

```java
public class DisjointSetUnion {
    private int[] parent;
    private int[] rank;
    private int[] size;
    
    public DisjointSetUnion(int n) {
        parent = new int[n + 1];
        rank = new int[n + 1];
        size = new int[n + 1];
        
        for (int i = 0; i <= n; i++) {
            parent[i] = i;
            size[i] = 1;
        }
    }
    
    public int findParent(int node) {
        if (node == parent[node]) {
            return node;
        }
        return parent[node] = findParent(parent[node]);
    }
    
    public void unionByRank(int u, int v) {
        int ulp_u = findParent(u);
        int ulp_v = findParent(v);
        
        if (ulp_u == ulp_v) return;
        
        if (rank[ulp_u] < rank[ulp_v]) {
            parent[ulp_u] = ulp_v;
        } else if (rank[ulp_v] < rank[ulp_u]) {
            parent[ulp_v] = ulp_u;
        } else {
            parent[ulp_v] = ulp_u;
            rank[ulp_u]++;
        }
    }
    
    public void unionBySize(int u, int v) {
        int ulp_u = findParent(u);
        int ulp_v = findParent(v);
        
        if (ulp_u == ulp_v) return;
        
        if (size[ulp_u] < size[ulp_v]) {
            parent[ulp_u] = ulp_v;
            size[ulp_v] += size[ulp_u];
        } else {
            parent[ulp_v] = ulp_u;
            size[ulp_u] += size[ulp_v];
        }
    }
}
```

### 33. Kruskal's Algorithm
**Time:** O(E log E) **Space:** O(V)

```java
import java.util.*;

public class KruskalMST {
    static class Edge {
        int src, dest, weight;
        
        Edge(int src, int dest, int weight) {
            this.src = src;
            this.dest = dest;
            this.weight = weight;
        }
    }
    
    public static int spanningTree(int V, int E, List<List<int[]>> adj) {
        List<Edge> edges = new ArrayList<>();
        
        for (int i = 0; i < V; i++) {
            for (int[] edge : adj.get(i)) {
                int adjNode = edge[0];
                int weight = edge[1];
                edges.add(new Edge(i, adjNode, weight));
            }
        }
        
        Collections.sort(edges, (a, b) -> a.weight - b.weight);
        
        DisjointSetUnion dsu = new DisjointSetUnion(V);
        int mstWeight = 0;
        
        for (Edge edge : edges) {
            if (dsu.findParent(edge.src) != dsu.findParent(edge.dest)) {
                mstWeight += edge.weight;
                dsu.unionBySize(edge.src, edge.dest);
            }
        }
        
        return mstWeight;
    }
}
```

### 34. Prim's Algorithm
**Time:** O(E log V) **Space:** O(V)

```java
import java.util.*;

public class PrimMST {
    public static int spanningTree(int V, int E, List<List<int[]>> adj) {
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        boolean[] inMST = new boolean[V];
        
        pq.offer(new int[]{0, 0});
        int mstWeight = 0;
        
        while (!pq.isEmpty()) {
            int[] current = pq.poll();
            int weight = current[0];
            int u = current[1];
            
            if (inMST[u]) continue;
            
            inMST[u] = true;
            mstWeight += weight;
            
            for (int[] edge : adj.get(u)) {
                int v = edge[0];
                int w = edge[1];
                
                if (!inMST[v]) {
                    pq.offer(new int[]{w, v});
                }
            }
        }
        
        return mstWeight;
    }
}
```

### 35. Number of Operations to Make Network Connected
**Time:** O(V + E) **Space:** O(V)

```java
public class NetworkConnected {
    public static int makeConnected(int n, int[][] connections) {
        if (connections.length < n - 1) return -1;
        
        DisjointSetUnion dsu = new DisjointSetUnion(n);
        
        for (int[] connection : connections) {
            dsu.unionBySize(connection[0], connection[1]);
        }
        
        int components = 0;
        for (int i = 0; i < n; i++) {
            if (dsu.findParent(i) == i) {
                components++;
            }
        }
        
        return components - 1;
    }
}
```

### 36. Most Stones Removed with Same Row or Column
**Time:** O(n × α(n)) **Space:** O(n)

```java
import java.util.*;

public class RemoveStones {
    public static int removeStones(int[][] stones) {
        int n = stones.length;
        int maxRow = 0;
        int maxCol = 0;
        
        for (int[] stone : stones) {
            maxRow = Math.max(maxRow, stone[0]);
            maxCol = Math.max(maxCol, stone[1]);
        }
        
        DisjointSetUnion dsu = new DisjointSetUnion(maxRow + maxCol + 1);
        Set<Integer> stoneNodes = new HashSet<>();
        
        for (int[] stone : stones) {
            int nodeRow = stone[0];
            int nodeCol = stone[1] + maxRow + 1;
            dsu.unionBySize(nodeRow, nodeCol);
            stoneNodes.add(nodeRow);
            stoneNodes.add(nodeCol);
        }
        
        int components = 0;
        for (int stoneNode : stoneNodes) {
            if (dsu.findParent(stoneNode) == stoneNode) {
                components++;
            }
        }
        
        return n - components;
    }
}
```

### 37. Accounts Merge
**Time:** O(N × M × α(N)) **Space:** O(N × M)

```java
import java.util.*;

public class AccountsMerge {
    public static List<List<String>> accountsMerge(List<List<String>> accounts) {
        int n = accounts.size();
        DisjointSetUnion dsu = new DisjointSetUnion(n);
        Map<String, Integer> emailToIndex = new HashMap<>();
        
        for (int i = 0; i < n; i++) {
            for (int j = 1; j < accounts.get(i).size(); j++) {
                String email = accounts.get(i).get(j);
                if (emailToIndex.containsKey(email)) {
                    dsu.unionBySize(i, emailToIndex.get(email));
                } else {
                    emailToIndex.put(email, i);
                }
            }
        }
        
        Map<Integer, List<String>> mergedEmails = new HashMap<>();
        for (String email : emailToIndex.keySet()) {
            int root = dsu.findParent(emailToIndex.get(email));
            mergedEmails.computeIfAbsent(root, k -> new ArrayList<>()).add(email);
        }
        
        List<List<String>> result = new ArrayList<>();
        for (Map.Entry<Integer, List<String>> entry : mergedEmails.entrySet()) {
            List<String> emails = entry.getValue();
            Collections.sort(emails);
            
            List<String> account = new ArrayList<>();
            account.add(accounts.get(entry.getKey()).get(0));
            account.addAll(emails);
            result.add(account);
        }
        
        return result;
    }
}
```

### 38. Number of Islands II
**Time:** O(k × α(m × n)) **Space:** O(m × n)

```java
import java.util.*;

public class NumberOfIslandsII {
    public static List<Integer> numIslands2(int m, int n, int[][] positions) {
        List<Integer> result = new ArrayList<>();
        DisjointSetUnion dsu = new DisjointSetUnion(m * n);
        boolean[][] grid = new boolean[m][n];
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        int islands = 0;
        
        for (int[] pos : positions) {
            int row = pos[0];
            int col = pos[1];
            
            if (grid[row][col]) {
                result.add(islands);
                continue;
            }
            
            grid[row][col] = true;
            islands++;
            
            for (int[] dir : directions) {
                int newRow = row + dir[0];
                int newCol = col + dir[1];
                
                if (newRow >= 0 && newRow < m && newCol >= 0 && newCol < n && grid[newRow][newCol]) {
                    int root1 = dsu.findParent(row * n + col);
                    int root2 = dsu.findParent(newRow * n + newCol);
                    
                    if (root1 != root2) {
                        dsu.unionBySize(root1, root2);
                        islands--;
                    }
                }
            }
            
            result.add(islands);
        }
        
        return result;
    }
}
```

### 39. Making a Large Island
**Time:** O(n²) **Space:** O(n²)

```java
import java.util.*;

public class MakingLargeIsland {
    public static int largestIsland(int[][] grid) {
        int n = grid.length;
        DisjointSetUnion dsu = new DisjointSetUnion(n * n);
        
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        for (int row = 0; row < n; row++) {
            for (int col = 0; col < n; col++) {
                if (grid[row][col] == 1) {
                    for (int[] dir : directions) {
                        int newRow = row + dir[0];
                        int newCol = col + dir[1];
                        
                        if (newRow >= 0 && newRow < n && newCol >= 0 && newCol < n && grid[newRow][newCol] == 1) {
                            int nodeNo = row * n + col;
                            int adjNodeNo = newRow * n + newCol;
                            dsu.unionBySize(nodeNo, adjNodeNo);
                        }
                    }
                }
            }
        }
        
        int maxSize = 0;
        for (int i = 0; i < n * n; i++) {
            maxSize = Math.max(maxSize, dsu.size[dsu.findParent(i)]);
        }
        
        for (int row = 0; row < n; row++) {
            for (int col = 0; col < n; col++) {
                if (grid[row][col] == 0) {
                    Set<Integer> components = new HashSet<>();
                    
                    for (int[] dir : directions) {
                        int newRow = row + dir[0];
                        int newCol = col + dir[1];
                        
                        if (newRow >= 0 && newRow < n && newCol >= 0 && newCol < n && grid[newRow][newCol] == 1) {
                            components.add(dsu.findParent(newRow * n + newCol));
                        }
                    }
                    
                    int totalSize = 1;
                    for (int parent : components) {
                        totalSize += dsu.size[parent];
                    }
                    
                    maxSize = Math.max(maxSize, totalSize);
                }
            }
        }
        
        return maxSize;
    }
}
```

### 40. Bridges in Graph (Tarjan's Algorithm)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class BridgesInGraph {
    private static int timer = 1;
    
    public static List<List<Integer>> criticalConnections(int n, List<List<Integer>> connections) {
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            adj.add(new ArrayList<>());
        }
        
        for (List<Integer> connection : connections) {
            adj.get(connection.get(0)).add(connection.get(1));
            adj.get(connection.get(1)).add(connection.get(0));
        }
        
        boolean[] visited = new boolean[n];
        int[] tin = new int[n];
        int[] low = new int[n];
        List<List<Integer>> bridges = new ArrayList<>();
        
        timer = 1;
        dfs(0, -1, adj, visited, tin, low, bridges);
        
        return bridges;
    }
    
    private static void dfs(int node, int parent, List<List<Integer>> adj, boolean[] visited,
                           int[] tin, int[] low, List<List<Integer>> bridges) {
        visited[node] = true;
        tin[node] = low[node] = timer;
        timer++;
        
        for (int neighbor : adj.get(node)) {
            if (neighbor == parent) continue;
            
            if (!visited[neighbor]) {
                dfs(neighbor, node, adj, visited, tin, low, bridges);
                low[node] = Math.min(low[node], low[neighbor]);
                
                if (low[neighbor] > tin[node]) {
                    bridges.add(Arrays.asList(node, neighbor));
                }
            } else {
                low[node] = Math.min(low[node], tin[neighbor]);
            }
        }
    }
}
```

### 41. Articulation Points (Tarjan's Algorithm)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class ArticulationPoints {
    private static int timer = 1;
    
    public static ArrayList<Integer> articulationPoints(int V, ArrayList<ArrayList<Integer>> adj) {
        boolean[] visited = new boolean[V];
        int[] tin = new int[V];
        int[] low = new int[V];
        boolean[] mark = new boolean[V];
        
        timer = 1;
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                dfs(i, -1, adj, visited, tin, low, mark);
            }
        }
        
        ArrayList<Integer> result = new ArrayList<>();
        for (int i = 0; i < V; i++) {
            if (mark[i]) {
                result.add(i);
            }
        }
        
        if (result.isEmpty()) {
            result.add(-1);
        }
        
        return result;
    }
    
    private static void dfs(int node, int parent, ArrayList<ArrayList<Integer>> adj,
                           boolean[] visited, int[] tin, int[] low, boolean[] mark) {
        visited[node] = true;
        tin[node] = low[node] = timer;
        timer++;
        int child = 0;
        
        for (int neighbor : adj.get(node)) {
            if (neighbor == parent) continue;
            
            if (!visited[neighbor]) {
                dfs(neighbor, node, adj, visited, tin, low, mark);
                low[node] = Math.min(low[node], low[neighbor]);
                
                if (low[neighbor] >= tin[node] && parent != -1) {
                    mark[node] = true;
                }
                child++;
            } else {
                low[node] = Math.min(low[node], tin[neighbor]);
            }
        }
        
        if (child > 1 && parent == -1) {
            mark[node] = true;
        }
    }
}
```

### 42. Kosaraju's Algorithm (Strongly Connected Components)
**Time:** O(V + E) **Space:** O(V)

```java
import java.util.*;

public class KosarajuAlgorithm {
    public static int kosaraju(int V, ArrayList<ArrayList<Integer>> adj) {
        Stack<Integer> stack = new Stack<>();
        boolean[] visited = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                dfs1(i, adj, visited, stack);
            }
        }
        
        ArrayList<ArrayList<Integer>> adjT = new ArrayList<>();
        for (int i = 0; i < V; i++) {
            adjT.add(new ArrayList<>());
        }
        
        for (int i = 0; i < V; i++) {
            visited[i] = false;
            for (int neighbor : adj.get(i)) {
                adjT.get(neighbor).add(i);
            }
        }
        
        int scc = 0;
        while (!stack.isEmpty()) {
            int node = stack.pop();
            if (!visited[node]) {
                scc++;
                dfs2(node, adjT, visited);
            }
        }
        
        return scc;
    }
    
    private static void dfs1(int node, ArrayList<ArrayList<Integer>> adj, boolean[] visited, Stack<Integer> stack) {
        visited[node] = true;
        
        for (int neighbor : adj.get(node)) {
            if (!visited[neighbor]) {
                dfs1(neighbor, adj, visited, stack);
            }
        }
        
        stack.push(node);
    }
    
    private static void dfs2(int node, ArrayList<ArrayList<Integer>> adjT, boolean[] visited) {
        visited[node] = true;
        
        for (int neighbor : adjT.get(node)) {
            if (!visited[neighbor]) {
                dfs2(neighbor, adjT, visited);
            }
        }
    }
}
```

### 43. Alien Dictionary

```java
public class AlienDictionary {
    public static String alienOrder(String[] words) {
        Map<Character, Set<Character>> adj = new HashMap<>();
        Map<Character, Integer> indegree = new HashMap<>();
        
        for (String word : words) {
            for (char c : word.toCharArray()) {
                adj.putIfAbsent(c, new HashSet<>());
                indegree.putIfAbsent(c, 0);
            }
        }
        
        for (int i = 0; i < words.length - 1; i++) {
            String word1 = words[i];
            String word2 = words[i + 1];
            
            if (word1.length() > word2.length() && word1.startsWith(word2)) {
                return "";
            }
            
            for (int j = 0; j < Math.min(word1.length(), word2.length()); j++) {
                char c1 = word1.charAt(j);
                char c2 = word2.charAt(j);
                
                if (c1 != c2) {
                    if (!adj.get(c1).contains(c2)) {
                        adj.get(c1).add(c2);
                        indegree.put(c2, indegree.get(c2) + 1);
                    }
                    break;
                }
            }
        }
        
        Queue<Character> queue = new LinkedList<>();
        for (char c : indegree.keySet()) {
            if (indegree.get(c) == 0) {
                queue.offer(c);
            }
        }
        
        StringBuilder result = new StringBuilder();
        while (!queue.isEmpty()) {
            char c = queue.poll();
            result.append(c);
            
            for (char neighbor : adj.get(c)) {
                indegree.put(neighbor, indegree.get(neighbor) - 1);
                if (indegree.get(neighbor) == 0) {
                    queue.offer(neighbor);
                }
            }
        }
        
        return result.length() == indegree.size() ? result.toString() : "";
    }
}
```

---


## Dynamic Programming

### 1. Fibonacci Numbers
**Time:** O(n) **Space:** O(n) / O(1)

```java
public class Fibonacci {
    public static int fib(int n) {
        if (n <= 1) return n;
        
        int[] dp = new int[n + 1];
        dp[0] = 0;
        dp[1] = 1;
        
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        
        return dp[n];
    }
    
    public static int fibSpaceOptimized(int n) {
        if (n <= 1) return n;
        
        int prev2 = 0;
        int prev1 = 1;
        
        for (int i = 2; i <= n; i++) {
            int current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        
        return prev1;
    }
}
```

### 2. Climbing Stairs
**Time:** O(n) **Space:** O(n) / O(1)

```java
public class ClimbingStairs {
    public static int climbStairs(int n) {
        if (n <= 1) return 1;
        
        int[] dp = new int[n + 1];
        dp[0] = 1;
        dp[1] = 1;
        
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        
        return dp[n];
    }
    
    public static int climbStairsSpaceOptimized(int n) {
        if (n <= 1) return 1;
        
        int prev2 = 1;
        int prev1 = 1;
        
        for (int i = 2; i <= n; i++) {
            int current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        
        return prev1;
    }
}
```

### 3. Frog Jump (Min Energy)
**Time:** O(n) **Space:** O(n) / O(1)

```java
import java.util.*;

public class FrogJump {
    public static int frogJump(int n, int[] heights) {
        int[] dp = new int[n];
        dp[0] = 0;
        
        for (int i = 1; i < n; i++) {
            int fs = dp[i - 1] + Math.abs(heights[i] - heights[i - 1]);
            int ss = Integer.MAX_VALUE;
            if (i > 1) {
                ss = dp[i - 2] + Math.abs(heights[i] - heights[i - 2]);
            }
            dp[i] = Math.min(fs, ss);
        }
        
        return dp[n - 1];
    }
    
    public static int frogJumpSpaceOptimized(int n, int[] heights) {
        int prev2 = 0;
        int prev1 = 0;
        
        for (int i = 1; i < n; i++) {
            int fs = prev1 + Math.abs(heights[i] - heights[i - 1]);
            int ss = Integer.MAX_VALUE;
            if (i > 1) {
                ss = prev2 + Math.abs(heights[i] - heights[i - 2]);
            }
            
            int current = Math.min(fs, ss);
            prev2 = prev1;
            prev1 = current;
        }
        
        return prev1;
    }
}
```

### 4. Frog Jump with K Distance
**Time:** O(n × k) **Space:** O(n) / O(k)

```java
import java.util.*;

public class FrogJumpK {
    public static int frogJumpK(int n, int[] heights, int k) {
        int[] dp = new int[n];
        dp[0] = 0;
        
        for (int i = 1; i < n; i++) {
            int minSteps = Integer.MAX_VALUE;
            
            for (int j = 1; j <= k && i - j >= 0; j++) {
                int jump = dp[i - j] + Math.abs(heights[i] - heights[i - j]);
                minSteps = Math.min(minSteps, jump);
            }
            
            dp[i] = minSteps;
        }
        
        return dp[n - 1];
    }
}
```

### 5. Maximum Sum of Non-Adjacent Elements
**Time:** O(n) **Space:** O(n) / O(1)

```java
import java.util.*;

public class MaxSumNonAdjacent {
    public static int maxSum(int[] arr) {
        int n = arr.length;
        if (n == 0) return 0;
        if (n == 1) return arr[0];
        
        int[] dp = new int[n];
        dp[0] = arr[0];
        dp[1] = Math.max(arr[0], arr[1]);
        
        for (int i = 2; i < n; i++) {
            dp[i] = Math.max(dp[i - 1], dp[i - 2] + arr[i]);
        }
        
        return dp[n - 1];
    }
    
    public static int maxSumSpaceOptimized(int[] arr) {
        int n = arr.length;
        if (n == 0) return 0;
        if (n == 1) return arr[0];
        
        int prev2 = arr[0];
        int prev1 = Math.max(arr[0], arr[1]);
        
        for (int i = 2; i < n; i++) {
            int current = Math.max(prev1, prev2 + arr[i]);
            prev2 = prev1;
            prev1 = current;
        }
        
        return prev1;
    }
}
```

### 6. House Robber II (Circular Array)
**Time:** O(n) **Space:** O(1)

```java
import java.util.*;

public class HouseRobberII {
    public static int rob(int[] nums) {
        int n = nums.length;
        if (n == 1) return nums[0];
        if (n == 2) return Math.max(nums[0], nums[1]);
        
        int robFirstHouse = robLinear(Arrays.copyOfRange(nums, 0, n - 1));
        int robLastHouse = robLinear(Arrays.copyOfRange(nums, 1, n));
        
        return Math.max(robFirstHouse, robLastHouse);
    }
    
    private static int robLinear(int[] arr) {
        int n = arr.length;
        if (n == 0) return 0;
        if (n == 1) return arr[0];
        
        int prev2 = arr[0];
        int prev1 = Math.max(arr[0], arr[1]);
        
        for (int i = 2; i < n; i++) {
            int current = Math.max(prev1, prev2 + arr[i]);
            prev2 = prev1;
            prev1 = current;
        }
        
        return prev1;
    }
}
```

### 7. Ninja's Training (2D DP)
**Time:** O(n × 4) **Space:** O(n × 4) / O(4)

```java
import java.util.*;

public class NinjaTraining {
    public static int ninjaTraining(int n, int[][] points) {
        int[][] dp = new int[n][4];
        
        dp[0][0] = Math.max(points[0][1], points[0][2]);
        dp[0][1] = Math.max(points[0][0], points[0][2]);
        dp[0][2] = Math.max(points[0][0], points[0][1]);
        dp[0][3] = Math.max(points[0][0], Math.max(points[0][1], points[0][2]));
        
        for (int day = 1; day < n; day++) {
            for (int last = 0; last < 4; last++) {
                dp[day][last] = 0;
                
                for (int task = 0; task < 3; task++) {
                    if (task != last) {
                        int activity = points[day][task] + dp[day - 1][task];
                        dp[day][last] = Math.max(dp[day][last], activity);
                    }
                }
            }
        }
        
        return dp[n - 1][3];
    }
    
    public static int ninjaTrainingSpaceOptimized(int n, int[][] points) {
        int[] prev = new int[4];
        
        prev[0] = Math.max(points[0][1], points[0][2]);
        prev[1] = Math.max(points[0][0], points[0][2]);
        prev[2] = Math.max(points[0][0], points[0][1]);
        prev[3] = Math.max(points[0][0], Math.max(points[0][1], points[0][2]));
        
        for (int day = 1; day < n; day++) {
            int[] temp = new int[4];
            
            for (int last = 0; last < 4; last++) {
                temp[last] = 0;
                
                for (int task = 0; task < 3; task++) {
                    if (task != last) {
                        int activity = points[day][task] + prev[task];
                        temp[last] = Math.max(temp[last], activity);
                    }
                }
            }
            
            prev = temp;
        }
        
        return prev[3];
    }
}
```

### 8. Grid Unique Paths
**Time:** O(m × n) **Space:** O(m × n) / O(n)

```java
public class GridUniquePaths {
    public static int uniquePaths(int m, int n) {
        int[][] dp = new int[m][n];
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) {
                    dp[i][j] = 1;
                    continue;
                }
                
                int up = 0, left = 0;
                if (i > 0) up = dp[i - 1][j];
                if (j > 0) left = dp[i][j - 1];
                
                dp[i][j] = up + left;
            }
        }
        
        return dp[m - 1][n - 1];
    }
    
    public static int uniquePathsSpaceOptimized(int m, int n) {
        int[] prev = new int[n];
        
        for (int i = 0; i < m; i++) {
            int[] temp = new int[n];
            
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) {
                    temp[j] = 1;
                    continue;
                }
                
                int up = 0, left = 0;
                if (i > 0) up = prev[j];
                if (j > 0) left = temp[j - 1];
                
                temp[j] = up + left;
            }
            
            prev = temp;
        }
        
        return prev[n - 1];
    }
    
    public static int uniquePathsMath(int m, int n) {
        int N = m + n - 2;
        int r = m - 1;
        double res = 1;
        
        for (int i = 1; i <= r; i++) {
            res = res * (N - r + i) / i;
        }
        
        return (int) res;
    }
}
```

### 9. Grid Unique Paths II (With Obstacles)
**Time:** O(m × n) **Space:** O(m × n) / O(n)

```java
public class GridUniquePathsII {
    public static int uniquePathsWithObstacles(int[][] obstacleGrid) {
        int m = obstacleGrid.length;
        int n = obstacleGrid[0].length;
        
        if (obstacleGrid[0][0] == 1) return 0;
        
        int[][] dp = new int[m][n];
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (obstacleGrid[i][j] == 1) {
                    dp[i][j] = 0;
                    continue;
                }
                
                if (i == 0 && j == 0) {
                    dp[i][j] = 1;
                    continue;
                }
                
                int up = 0, left = 0;
                if (i > 0) up = dp[i - 1][j];
                if (j > 0) left = dp[i][j - 1];
                
                dp[i][j] = up + left;
            }
        }
        
        return dp[m - 1][n - 1];
    }
    
    public static int uniquePathsWithObstaclesSpaceOptimized(int[][] obstacleGrid) {
        int m = obstacleGrid.length;
        int n = obstacleGrid[0].length;
        
        int[] prev = new int[n];
        
        for (int i = 0; i < m; i++) {
            int[] temp = new int[n];
            
            for (int j = 0; j < n; j++) {
                if (obstacleGrid[i][j] == 1) {
                    temp[j] = 0;
                    continue;
                }
                
                if (i == 0 && j == 0) {
                    temp[j] = 1;
                    continue;
                }
                
                int up = 0, left = 0;
                if (i > 0) up = prev[j];
                if (j > 0) left = temp[j - 1];
                
                temp[j] = up + left;
            }
            
            prev = temp;
        }
        
        return prev[n - 1];
    }
}
```

### 10. Minimum Path Sum
**Time:** O(m × n) **Space:** O(m × n) / O(n)

```java
public class MinimumPathSum {
    public static int minPathSum(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        
        int[][] dp = new int[m][n];
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) {
                    dp[i][j] = grid[i][j];
                    continue;
                }
                
                int up = Integer.MAX_VALUE, left = Integer.MAX_VALUE;
                if (i > 0) up = dp[i - 1][j];
                if (j > 0) left = dp[i][j - 1];
                
                dp[i][j] = grid[i][j] + Math.min(up, left);
            }
        }
        
        return dp[m - 1][n - 1];
    }
    
    public static int minPathSumSpaceOptimized(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        
        int[] prev = new int[n];
        
        for (int i = 0; i < m; i++) {
            int[] temp = new int[n];
            
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) {
                    temp[j] = grid[i][j];
                    continue;
                }
                
                int up = Integer.MAX_VALUE, left = Integer.MAX_VALUE;
                if (i > 0) up = prev[j];
                if (j > 0) left = temp[j - 1];
                
                temp[j] = grid[i][j] + Math.min(up, left);
            }
            
            prev = temp;
        }
        
        return prev[n - 1];
    }
}
```

### 11. Triangle
**Time:** O(n²) **Space:** O(n²) / O(n)

```java
import java.util.*;

public class Triangle {
    public static int minimumTotal(List<List<Integer>> triangle) {
        int n = triangle.size();
        int[][] dp = new int[n][n];
        
        for (int j = 0; j < n; j++) {
            dp[n - 1][j] = triangle.get(n - 1).get(j);
        }
        
        for (int i = n - 2; i >= 0; i--) {
            for (int j = i; j >= 0; j--) {
                int down = dp[i + 1][j];
                int diagonal = dp[i + 1][j + 1];
                
                dp[i][j] = triangle.get(i).get(j) + Math.min(down, diagonal);
            }
        }
        
        return dp[0][0];
    }
    
    public static int minimumTotalSpaceOptimized(List<List<Integer>> triangle) {
        int n = triangle.size();
        int[] front = new int[n];
        
        for (int j = 0; j < n; j++) {
            front[j] = triangle.get(n - 1).get(j);
        }
        
        for (int i = n - 2; i >= 0; i--) {
            for (int j = i; j >= 0; j--) {
                int down = front[j];
                int diagonal = front[j + 1];
                
                front[j] = triangle.get(i).get(j) + Math.min(down, diagonal);
            }
        }
        
        return front[0];
    }
}
```

### 12. Minimum Falling Path Sum
**Time:** O(n²) **Space:** O(n²) / O(n)

```java
public class MinimumFallingPathSum {
    public static int minFallingPathSum(int[][] matrix) {
        int n = matrix.length;
        int[][] dp = new int[n][n];
        
        for (int j = 0; j < n; j++) {
            dp[0][j] = matrix[0][j];
        }
        
        for (int i = 1; i < n; i++) {
            for (int j = 0; j < n; j++) {
                int up = dp[i - 1][j];
                
                int leftDiag = Integer.MAX_VALUE;
                if (j - 1 >= 0) leftDiag = dp[i - 1][j - 1];
                
                int rightDiag = Integer.MAX_VALUE;
                if (j + 1 < n) rightDiag = dp[i - 1][j + 1];
                
                dp[i][j] = matrix[i][j] + Math.min(up, Math.min(leftDiag, rightDiag));
            }
        }
        
        int result = Integer.MAX_VALUE;
        for (int j = 0; j < n; j++) {
            result = Math.min(result, dp[n - 1][j]);
        }
        
        return result;
    }
    
    public static int minFallingPathSumSpaceOptimized(int[][] matrix) {
        int n = matrix.length;
        int[] prev = new int[n];
        
        for (int j = 0; j < n; j++) {
            prev[j] = matrix[0][j];
        }
        
        for (int i = 1; i < n; i++) {
            int[] temp = new int[n];
            
            for (int j = 0; j < n; j++) {
                int up = prev[j];
                
                int leftDiag = Integer.MAX_VALUE;
                if (j - 1 >= 0) leftDiag = prev[j - 1];
                
                int rightDiag = Integer.MAX_VALUE;
                if (j + 1 < n) rightDiag = prev[j + 1];
                
                temp[j] = matrix[i][j] + Math.min(up, Math.min(leftDiag, rightDiag));
            }
            
            prev = temp;
        }
        
        int result = Integer.MAX_VALUE;
        for (int j = 0; j < n; j++) {
            result = Math.min(result, prev[j]);
        }
        
        return result;
    }
}
```

### 13. Cherry Pickup (3D DP)
**Time:** O(n × m × m) **Space:** O(n × m × m) / O(m × m)

```java
public class CherryPickup {
    public static int cherryPickup(int[][] grid) {
        int n = grid.length;
        int m = grid[0].length;
        
        int[][][] dp = new int[n][m][m];
        
        for (int j1 = 0; j1 < m; j1++) {
            for (int j2 = 0; j2 < m; j2++) {
                if (j1 == j2) {
                    dp[n - 1][j1][j2] = grid[n - 1][j1];
                } else {
                    dp[n - 1][j1][j2] = grid[n - 1][j1] + grid[n - 1][j2];
                }
            }
        }
        
        for (int i = n - 2; i >= 0; i--) {
            for (int j1 = 0; j1 < m; j1++) {
                for (int j2 = 0; j2 < m; j2++) {
                    int maxi = Integer.MIN_VALUE;
                    
                    for (int di = -1; di <= 1; di++) {
                        for (int dj = -1; dj <= 1; dj++) {
                            int ans;
                            
                            if (j1 == j2) {
                                ans = grid[i][j1];
                            } else {
                                ans = grid[i][j1] + grid[i][j2];
                            }
                            
                            if ((j1 + di < 0 || j1 + di >= m) || (j2 + dj < 0 || j2 + dj >= m)) {
                                ans += -1e9;
                            } else {
                                ans += dp[i + 1][j1 + di][j2 + dj];
                            }
                            
                            maxi = Math.max(ans, maxi);
                        }
                    }
                    
                    dp[i][j1][j2] = maxi;
                }
            }
        }
        
        return dp[0][0][m - 1];
    }
    
    public static int cherryPickupSpaceOptimized(int[][] grid) {
        int n = grid.length;
        int m = grid[0].length;
        
        int[][] front = new int[m][m];
        int[][] curr = new int[m][m];
        
        for (int j1 = 0; j1 < m; j1++) {
            for (int j2 = 0; j2 < m; j2++) {
                if (j1 == j2) {
                    front[j1][j2] = grid[n - 1][j1];
                } else {
                    front[j1][j2] = grid[n - 1][j1] + grid[n - 1][j2];
                }
            }
        }
        
        for (int i = n - 2; i >= 0; i--) {
            for (int j1 = 0; j1 < m; j1++) {
                for (int j2 = 0; j2 < m; j2++) {
                    int maxi = Integer.MIN_VALUE;
                    
                    for (int di = -1; di <= 1; di++) {
                        for (int dj = -1; dj <= 1; dj++) {
                            int ans;
                            
                            if (j1 == j2) {
                                ans = grid[i][j1];
                            } else {
                                ans = grid[i][j1] + grid[i][j2];
                            }
                            
                            if ((j1 + di < 0 || j1 + di >= m) || (j2 + dj < 0 || j2 + dj >= m)) {
                                ans += (int) (-1e9);
                            } else {
                                ans += front[j1 + di][j2 + dj];
                            }
                            
                            maxi = Math.max(ans, maxi);
                        }
                    }
                    
                    curr[j1][j2] = maxi;
                }
            }
            
            for (int a = 0; a < m; a++) {
                front[a] = curr[a].clone();
            }
        }
        
        return front[0][m - 1];
    }
}
```

### 14. Subset 2D/3D DP Problems

```java
// Subset Sum Equal to K
public class SubsetSum {
    public static boolean subsetSumToK(int n, int k, int[] arr) {
        boolean[][] dp = new boolean[n][k + 1];
        
        for (int i = 0; i < n; i++) {
            dp[i][0] = true;
        }
        
        if (arr[0] <= k) {
            dp[0][arr[0]] = true;
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int target = 1; target <= k; target++) {
                boolean notTaken = dp[ind - 1][target];
                boolean taken = false;
                if (arr[ind] <= target) {
                    taken = dp[ind - 1][target - arr[ind]];
                }
                
                dp[ind][target] = notTaken || taken;
            }
        }
        
        return dp[n - 1][k];
    }
}

// Partition Equal Subset Sum
public class PartitionEqualSubsetSum {
    public static boolean canPartition(int[] nums) {
        int totalSum = 0;
        for (int num : nums) {
            totalSum += num;
        }
        
        if (totalSum % 2 == 1) return false;
        
        int target = totalSum / 2;
        boolean[] prev = new boolean[target + 1];
        
        prev[0] = true;
        if (nums[0] <= target) {
            prev[nums[0]] = true;
        }
        
        for (int ind = 1; ind < nums.length; ind++) {
            boolean[] cur = new boolean[target + 1];
            cur[0] = true;
            
            for (int i = 1; i <= target; i++) {
                boolean notTaken = prev[i];
                boolean taken = false;
                if (nums[ind] <= i) {
                    taken = prev[i - nums[ind]];
                }
                
                cur[i] = notTaken || taken;
            }
            
            prev = cur;
        }
        
        return prev[target];
    }
}
```


### 15. Grid Unique Paths
**Time:** O(m × n) **Space:** O(m × n) / O(n)

```java
public class GridPaths {
    public static int uniquePaths(int m, int n) {
        int[][] dp = new int[m][n];
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) {
                    dp[i][j] = 1;
                } else {
                    int up = 0, left = 0;
                    if (i > 0) up = dp[i - 1][j];
                    if (j > 0) left = dp[i][j - 1];
                    dp[i][j] = up + left;
                }
            }
        }
        
        return dp[m - 1][n - 1];
    }
}
```

### 16. Grid Unique Paths II
**Time:** O(m × n) **Space:** O(m × n) / O(n)

```java
public class GridPathsObstacles {
    public static int uniquePathsWithObstacles(int[][] obstacleGrid) {
        int m = obstacleGrid.length;
        int n = obstacleGrid[0].length;
        
        int[] prev = new int[n];
        
        for (int i = 0; i < m; i++) {
            int[] temp = new int[n];
            
            for (int j = 0; j < n; j++) {
                if (obstacleGrid[i][j] == 1) {
                    temp[j] = 0;
                } else if (i == 0 && j == 0) {
                    temp[j] = 1;
                } else {
                    int up = 0, left = 0;
                    if (i > 0) up = prev[j];
                    if (j > 0) left = temp[j - 1];
                    temp[j] = up + left;
                }
            }
            
            prev = temp;
        }
        
        return prev[n - 1];
    }
}
```

### 17. Grid Problems

```java
// Minimum Path Sum
public class MinPathSum {
    public static int minPathSum(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) continue;
                
                int up = Integer.MAX_VALUE, left = Integer.MAX_VALUE;
                if (i > 0) up = grid[i - 1][j];
                if (j > 0) left = grid[i][j - 1];
                
                grid[i][j] += Math.min(up, left);
            }
        }
        
        return grid[m - 1][n - 1];
    }
}

// Dungeon Game
public class DungeonGame {
    public static int calculateMinimumHP(int[][] dungeon) {
        int m = dungeon.length;
        int n = dungeon[0].length;
        
        int[][] dp = new int[m + 1][n + 1];
        
        for (int i = 0; i <= m; i++) {
            for (int j = 0; j <= n; j++) {
                dp[i][j] = Integer.MAX_VALUE;
            }
        }
        
        dp[m][n - 1] = dp[m - 1][n] = 1;
        
        for (int i = m - 1; i >= 0; i--) {
            for (int j = n - 1; j >= 0; j--) {
                int need = Math.min(dp[i + 1][j], dp[i][j + 1]) - dungeon[i][j];
                dp[i][j] = need <= 0 ? 1 : need;
            }
        }
        
        return dp[0][0];
    }
}
```

### 18. Subset Sum Equal to K
**Time:** O(n × k) **Space:** O(n × k) / O(k)

```java
public class SubsetSum {
    public static boolean subsetSumToK(int n, int k, int[] arr) {
        boolean[][] dp = new boolean[n][k + 1];
        
        for (int i = 0; i < n; i++) {
            dp[i][0] = true;
        }
        
        if (arr[0] <= k) {
            dp[0][arr[0]] = true;
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int target = 1; target <= k; target++) {
                boolean notTaken = dp[ind - 1][target];
                boolean taken = false;
                if (arr[ind] <= target) {
                    taken = dp[ind - 1][target - arr[ind]];
                }
                
                dp[ind][target] = notTaken || taken;
            }
        }
        
        return dp[n - 1][k];
    }
    
    public static boolean subsetSumToKSpaceOptimized(int n, int k, int[] arr) {
        boolean[] prev = new boolean[k + 1];
        
        prev[0] = true;
        if (arr[0] <= k) {
            prev[arr[0]] = true;
        }
        
        for (int ind = 1; ind < n; ind++) {
            boolean[] cur = new boolean[k + 1];
            cur[0] = true;
            
            for (int target = 1; target <= k; target++) {
                boolean notTaken = prev[target];
                boolean taken = false;
                if (arr[ind] <= target) {
                    taken = prev[target - arr[ind]];
                }
                
                cur[target] = notTaken || taken;
            }
            
            prev = cur;
        }
        
        return prev[k];
    }
}
```

### 19. Partition Equal Subset Sum
**Time:** O(n × sum) **Space:** O(n × sum) / O(sum)

```java
public class PartitionEqualSubsetSum {
    public static boolean canPartition(int[] nums) {
        int totalSum = 0;
        for (int num : nums) {
            totalSum += num;
        }
        
        if (totalSum % 2 == 1) return false;
        
        int target = totalSum / 2;
        boolean[] prev = new boolean[target + 1];
        
        prev[0] = true;
        if (nums[0] <= target) {
            prev[nums[0]] = true;
        }
        
        for (int ind = 1; ind < nums.length; ind++) {
            boolean[] cur = new boolean[target + 1];
            cur[0] = true;
            
            for (int i = 1; i <= target; i++) {
                boolean notTaken = prev[i];
                boolean taken = false;
                if (nums[ind] <= i) {
                    taken = prev[i - nums[ind]];
                }
                
                cur[i] = notTaken || taken;
            }
            
            prev = cur;
        }
        
        return prev[target];
    }
}
```

### 20. Count Subsets with Sum K
**Time:** O(n × k) **Space:** O(n × k) / O(k)

```java
public class CountSubsetsWithSumK {
    public static int findWays(int[] arr, int k) {
        int n = arr.length;
        int[][] dp = new int[n][k + 1];
        
        for (int i = 0; i < n; i++) {
            dp[i][0] = 1;
        }
        
        if (arr[0] <= k) {
            dp[0][arr[0]] = 1;
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int target = 0; target <= k; target++) {
                int notTaken = dp[ind - 1][target];
                int taken = 0;
                if (arr[ind] <= target) {
                    taken = dp[ind - 1][target - arr[ind]];
                }
                
                dp[ind][target] = notTaken + taken;
            }
        }
        
        return dp[n - 1][k];
    }
    
    public static int findWaysSpaceOptimized(int[] arr, int k) {
        int n = arr.length;
        int[] prev = new int[k + 1];
        
        prev[0] = 1;
        if (arr[0] <= k) {
            prev[arr[0]] = 1;
        }
        
        for (int ind = 1; ind < n; ind++) {
            int[] cur = new int[k + 1];
            cur[0] = 1;
            
            for (int target = 0; target <= k; target++) {
                int notTaken = prev[target];
                int taken = 0;
                if (arr[ind] <= target) {
                    taken = prev[target - arr[ind]];
                }
                
                cur[target] = notTaken + taken;
            }
            
            prev = cur;
        }
        
        return prev[k];
    }
}
```

### 21. Partition with Given Difference
**Time:** O(n × sum) **Space:** O(n × sum) / O(sum)

```java
public class PartitionWithGivenDifference {
    public static int countPartitions(int n, int d, int[] arr) {
        int totSum = 0;
        for (int i = 0; i < arr.length; i++) {
            totSum += arr[i];
        }
        
        if (totSum - d < 0) return 0;
        if ((totSum - d) % 2 == 1) return 0;
        
        int s2 = (totSum - d) / 2;
        
        return findWays(arr, s2);
    }
    
    private static int findWays(int[] arr, int k) {
        int n = arr.length;
        int[] prev = new int[k + 1];
        
        if (arr[0] == 0) prev[0] = 2;
        else prev[0] = 1;
        
        if (arr[0] != 0 && arr[0] <= k) {
            prev[arr[0]] = 1;
        }
        
        for (int ind = 1; ind < n; ind++) {
            int[] cur = new int[k + 1];
            
            for (int target = 0; target <= k; target++) {
                int notTaken = prev[target];
                int taken = 0;
                if (arr[ind] <= target) {
                    taken = prev[target - arr[ind]];
                }
                
                cur[target] = (notTaken + taken) % 1000000007;
            }
            
            prev = cur;
        }
        
        return prev[k];
    }
}
```

### 22. 0/1 Knapsack
**Time:** O(n × W) **Space:** O(n × W) / O(W)

```java
public class Knapsack01 {
    public static int knapsack(int[] weight, int[] value, int n, int maxWeight) {
        int[][] dp = new int[n][maxWeight + 1];
        
        for (int w = weight[0]; w <= maxWeight; w++) {
            dp[0][w] = value[0];
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int w = 0; w <= maxWeight; w++) {
                int notTaken = dp[ind - 1][w];
                int taken = Integer.MIN_VALUE;
                if (weight[ind] <= w) {
                    taken = value[ind] + dp[ind - 1][w - weight[ind]];
                }
                
                dp[ind][w] = Math.max(notTaken, taken);
            }
        }
        
        return dp[n - 1][maxWeight];
    }
    
    public static int knapsackSpaceOptimized(int[] weight, int[] value, int n, int maxWeight) {
        int[] prev = new int[maxWeight + 1];
        
        for (int w = weight[0]; w <= maxWeight; w++) {
            prev[w] = value[0];
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int w = maxWeight; w >= 0; w--) {
                int notTaken = prev[w];
                int taken = Integer.MIN_VALUE;
                if (weight[ind] <= w) {
                    taken = value[ind] + prev[w - weight[ind]];
                }
                
                prev[w] = Math.max(notTaken, taken);
            }
        }
        
        return prev[maxWeight];
    }
}
```

### 23. Minimum Coins
**Time:** O(n × amount) **Space:** O(n × amount) / O(amount)

```java
import java.util.*;

public class MinimumCoins {
    public static int coinChange(int[] coins, int amount) {
        int n = coins.length;
        int[][] dp = new int[n][amount + 1];
        
        for (int T = 0; T <= amount; T++) {
            if (T % coins[0] == 0) {
                dp[0][T] = T / coins[0];
            } else {
                dp[0][T] = (int) Math.pow(10, 9);
            }
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int T = 0; T <= amount; T++) {
                int notTake = dp[ind - 1][T];
                int take = (int) Math.pow(10, 9);
                if (coins[ind] <= T) {
                    take = 1 + dp[ind][T - coins[ind]];
                }
                
                dp[ind][T] = Math.min(notTake, take);
            }
        }
        
        int ans = dp[n - 1][amount];
        if (ans >= (int) Math.pow(10, 9)) return -1;
        return ans;
    }
    
    public static int coinChangeSpaceOptimized(int[] coins, int amount) {
        int n = coins.length;
        int[] prev = new int[amount + 1];
        int[] cur = new int[amount + 1];
        
        for (int T = 0; T <= amount; T++) {
            if (T % coins[0] == 0) {
                prev[T] = T / coins[0];
            } else {
                prev[T] = (int) Math.pow(10, 9);
            }
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int T = 0; T <= amount; T++) {
                int notTake = prev[T];
                int take = (int) Math.pow(10, 9);
                if (coins[ind] <= T) {
                    take = 1 + cur[T - coins[ind]];
                }
                
                cur[T] = Math.min(notTake, take);
            }
            
            prev = cur;
        }
        
        int ans = prev[amount];
        if (ans >= (int) Math.pow(10, 9)) return -1;
        return ans;
    }
}
```

### 24. Target Sum
**Time:** O(n × sum) **Space:** O(n × sum) / O(sum)

```java
public class TargetSum {
    public static int targetSum(int n, int target, int[] arr) {
        int totSum = 0;
        for (int i = 0; i < arr.length; i++) {
            totSum += arr[i];
        }
        
        if (totSum - target < 0) return 0;
        if ((totSum - target) % 2 == 1) return 0;
        
        int s2 = (totSum - target) / 2;
        
        return findWays(arr, s2);
    }
    
    private static int findWays(int[] arr, int k) {
        int n = arr.length;
        int[] prev = new int[k + 1];
        
        if (arr[0] == 0) prev[0] = 2;
        else prev[0] = 1;
        
        if (arr[0] != 0 && arr[0] <= k) {
            prev[arr[0]] = 1;
        }
        
        for (int ind = 1; ind < n; ind++) {
            int[] cur = new int[k + 1];
            
            for (int target = 0; target <= k; target++) {
                int notTaken = prev[target];
                int taken = 0;
                if (arr[ind] <= target) {
                    taken = prev[target - arr[ind]];
                }
                
                cur[target] = (notTaken + taken);
            }
            
            prev = cur;
        }
        
        return prev[k];
    }
}
```

### 25. Coin Change II (Ways to Make Amount)
**Time:** O(n × amount) **Space:** O(n × amount) / O(amount)

```java
public class CoinChangeII {
    public static int change(int amount, int[] coins) {
        int n = coins.length;
        int[][] dp = new int[n][amount + 1];
        
        for (int T = 0; T <= amount; T++) {
            if (T % coins[0] == 0) {
                dp[0][T] = 1;
            }
        }
        
        for (int ind = 1; ind < n; ind++) {
            for (int T = 0; T <= amount; T++) {
                int notTaken = dp[ind - 1][T];
                int taken = 0;
                if (coins[ind] <= T) {
                    taken = dp[ind][T - coins[ind]];
                }
                
                dp[ind][T] = notTaken + taken;
            }
        }
        
        return dp[n - 1][amount];
    }
    
    public static int changeSpaceOptimized(int amount, int[] coins) {
        int[] prev = new int[amount + 1];
        
        for (int T = 0; T <= amount; T++) {
            if (T % coins[0] == 0) {
                prev[T] = 1;
            }
        }
        
        for (int ind = 1; ind < coins.length; ind++) {
            int[] cur = new int[amount + 1];
            
            for (int T = 0; T <= amount; T++) {
                int notTaken = prev[T];
                int taken = 0;
                if (coins[ind] <= T) {
                    taken = cur[T - coins[ind]];
                }
                
                cur[T] = notTaken + taken;
            }
            
            prev = cur;
        }
        
        return prev[amount];
    }
}
```

### 26. Longest Common Subsequence
**Time:** O(n × m) **Space:** O(n × m) / O(m)

```java
public class LongestCommonSubsequence {
    public static int longestCommonSubsequence(String text1, String text2) {
        int n = text1.length();
        int m = text2.length();
        
        int[][] dp = new int[n + 1][m + 1];
        
        for (int ind1 = 1; ind1 <= n; ind1++) {
            for (int ind2 = 1; ind2 <= m; ind2++) {
                if (text1.charAt(ind1 - 1) == text2.charAt(ind2 - 1)) {
                    dp[ind1][ind2] = 1 + dp[ind1 - 1][ind2 - 1];
                } else {
                    dp[ind1][ind2] = Math.max(dp[ind1 - 1][ind2], dp[ind1][ind2 - 1]);
                }
            }
        }
        
        return dp[n][m];
    }
    
    public static int longestCommonSubsequenceSpaceOptimized(String text1, String text2) {
        int n = text1.length();
        int m = text2.length();
        
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        
        for (int ind1 = 1; ind1 <= n; ind1++) {
            for (int ind2 = 1; ind2 <= m; ind2++) {
                if (text1.charAt(ind1 - 1) == text2.charAt(ind2 - 1)) {
                    cur[ind2] = 1 + prev[ind2 - 1];
                } else {
                    cur[ind2] = Math.max(prev[ind2], cur[ind2 - 1]);
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 27. Print Longest Common Subsequence
**Time:** O(n × m) **Space:** O(n × m)

```java
public class PrintLCS {
    public static String printLCS(String s1, String s2) {
        int n = s1.length();
        int m = s2.length();
        
        int[][] dp = new int[n + 1][m + 1];
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        
        int len = dp[n][m];
        int i = n;
        int j = m;
        
        int index = len - 1;
        String str = "";
        for (int k = 1; k <= len; k++) {
            str += "$";
        }
        StringBuilder ss = new StringBuilder(s1);
        StringBuilder str2 = new StringBuilder(str);
        
        while (i > 0 && j > 0) {
            if (ss.charAt(i - 1) == s2.charAt(j - 1)) {
                str2.setCharAt(index, ss.charAt(i - 1));
                index--;
                i--;
                j--;
            } else if (dp[i - 1][j] > dp[i][j - 1]) {
                i--;
            } else {
                j--;
            }
        }
        
        return str2.toString();
    }
}
```

### 28. Longest Common Substring
**Time:** O(n × m) **Space:** O(n × m) / O(m)

```java
public class LongestCommonSubstring {
    public static int longestCommonSubstr(String s1, String s2, int n, int m) {
        int[][] dp = new int[n + 1][m + 1];
        int ans = 0;
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                    ans = Math.max(ans, dp[i][j]);
                } else {
                    dp[i][j] = 0;
                }
            }
        }
        
        return ans;
    }
    
    public static int longestCommonSubstrSpaceOptimized(String s1, String s2, int n, int m) {
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        int ans = 0;
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    cur[j] = 1 + prev[j - 1];
                    ans = Math.max(ans, cur[j]);
                } else {
                    cur[j] = 0;
                }
            }
            
            prev = cur.clone();
        }
        
        return ans;
    }
}
```

### 29. Longest Palindromic Subsequence
**Time:** O(n²) **Space:** O(n²) / O(n)

```java
public class LongestPalindromicSubsequence {
    public static int longestPalindromeSubseq(String s) {
        String t = new StringBuilder(s).reverse().toString();
        return longestCommonSubsequence(s, t);
    }
    
    private static int longestCommonSubsequence(String s1, String s2) {
        int n = s1.length();
        int m = s2.length();
        
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    cur[j] = 1 + prev[j - 1];
                } else {
                    cur[j] = Math.max(prev[j], cur[j - 1]);
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 30. Minimum Insertions to Make String Palindrome
**Time:** O(n²) **Space:** O(n²) / O(n)

```java
public class MinimumInsertions {
    public static int minInsertions(String s) {
        int n = s.length();
        int k = longestPalindromeSubseq(s);
        return n - k;
    }
    
    private static int longestPalindromeSubseq(String s) {
        String t = new StringBuilder(s).reverse().toString();
        return longestCommonSubsequence(s, t);
    }
    
    private static int longestCommonSubsequence(String s1, String s2) {
        int n = s1.length();
        int m = s2.length();
        
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    cur[j] = 1 + prev[j - 1];
                } else {
                    cur[j] = Math.max(prev[j], cur[j - 1]);
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 31. Minimum Deletions to Make String Palindrome
**Time:** O(n²) **Space:** O(n²) / O(n)

```java
public class MinimumDeletions {
    public static int minDeletions(String s) {
        int n = s.length();
        int k = longestPalindromeSubseq(s);
        return n - k;
    }
    
    private static int longestPalindromeSubseq(String s) {
        String t = new StringBuilder(s).reverse().toString();
        return longestCommonSubsequence(s, t);
    }
    
    private static int longestCommonSubsequence(String s1, String s2) {
        int n = s1.length();
        int m = s2.length();
        
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    cur[j] = 1 + prev[j - 1];
                } else {
                    cur[j] = Math.max(prev[j], cur[j - 1]);
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 32. Shortest Common Supersequence
**Time:** O(n × m) **Space:** O(n × m)

```java
public class ShortestCommonSupersequence {
    public static String shortestCommonSupersequence(String str1, String str2) {
        int n = str1.length();
        int m = str2.length();
        
        int[][] dp = new int[n + 1][m + 1];
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (str1.charAt(i - 1) == str2.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        
        int i = n, j = m;
        String ans = "";
        
        while (i > 0 && j > 0) {
            if (str1.charAt(i - 1) == str2.charAt(j - 1)) {
                ans = str1.charAt(i - 1) + ans;
                i--;
                j--;
            } else if (dp[i - 1][j] > dp[i][j - 1]) {
                ans = str1.charAt(i - 1) + ans;
                i--;
            } else {
                ans = str2.charAt(j - 1) + ans;
                j--;
            }
        }
        
        while (i > 0) {
            ans = str1.charAt(i - 1) + ans;
            i--;
        }
        
        while (j > 0) {
            ans = str2.charAt(j - 1) + ans;
            j--;
        }
        
        return ans;
    }
}
```

### 33. Distinct Subsequences
**Time:** O(n × m) **Space:** O(n × m) / O(m)

```java
public class DistinctSubsequences {
    public static int numDistinct(String s, String t) {
        int n = s.length();
        int m = t.length();
        
        int[][] dp = new int[n + 1][m + 1];
        
        for (int i = 0; i <= n; i++) {
            dp[i][0] = 1;
        }
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s.charAt(i - 1) == t.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1] + dp[i - 1][j];
                } else {
                    dp[i][j] = dp[i - 1][j];
                }
            }
        }
        
        return dp[n][m];
    }
    
    public static int numDistinctSpaceOptimized(String s, String t) {
        int n = s.length();
        int m = t.length();
        
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        
        prev[0] = cur[0] = 1;
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (s.charAt(i - 1) == t.charAt(j - 1)) {
                    cur[j] = prev[j - 1] + prev[j];
                } else {
                    cur[j] = prev[j];
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 34. Edit Distance
**Time:** O(n × m) **Space:** O(n × m) / O(m)

```java
public class EditDistance {
    public static int minDistance(String word1, String word2) {
        int n = word1.length();
        int m = word2.length();
        
        int[][] dp = new int[n + 1][m + 1];
        
        for (int i = 0; i <= n; i++) {
            dp[i][0] = i;
        }
        
        for (int j = 0; j <= m; j++) {
            dp[0][j] = j;
        }
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (word1.charAt(i - 1) == word2.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1];
                } else {
                    dp[i][j] = 1 + Math.min(dp[i - 1][j - 1], Math.min(dp[i - 1][j], dp[i][j - 1]));
                }
            }
        }
        
        return dp[n][m];
    }
    
    public static int minDistanceSpaceOptimized(String word1, String word2) {
        int n = word1.length();
        int m = word2.length();
        
        int[] prev = new int[m + 1];
        int[] cur = new int[m + 1];
        
        for (int j = 0; j <= m; j++) {
            prev[j] = j;
        }
        
        for (int i = 1; i <= n; i++) {
            cur[0] = i;
            
            for (int j = 1; j <= m; j++) {
                if (word1.charAt(i - 1) == word2.charAt(j - 1)) {
                    cur[j] = prev[j - 1];
                } else {
                    cur[j] = 1 + Math.min(prev[j - 1], Math.min(prev[j], cur[j - 1]));
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 35. Wildcard Matching
**Time:** O(n × m) **Space:** O(n × m) / O(m)

```java
public class WildcardMatching {
    public static boolean isMatch(String s, String p) {
        int n = s.length();
        int m = p.length();
        
        boolean[][] dp = new boolean[n + 1][m + 1];
        
        dp[0][0] = true;
        
        for (int j = 1; j <= m; j++) {
            boolean flag = true;
            for (int ii = 1; ii <= j; ii++) {
                if (p.charAt(ii - 1) != '*') {
                    flag = false;
                    break;
                }
            }
            dp[0][j] = flag;
        }
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (p.charAt(j - 1) == '*') {
                    dp[i][j] = dp[i - 1][j] || dp[i][j - 1];
                } else if (p.charAt(j - 1) == '?' || s.charAt(i - 1) == p.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1];
                } else {
                    dp[i][j] = false;
                }
            }
        }
        
        return dp[n][m];
    }
    
    public static boolean isMatchSpaceOptimized(String s, String p) {
        int n = s.length();
        int m = p.length();
        
        boolean[] prev = new boolean[m + 1];
        boolean[] cur = new boolean[m + 1];
        
        prev[0] = true;
        
        for (int j = 1; j <= m; j++) {
            boolean flag = true;
            for (int ii = 1; ii <= j; ii++) {
                if (p.charAt(ii - 1) != '*') {
                    flag = false;
                    break;
                }
            }
            prev[j] = flag;
        }
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (p.charAt(j - 1) == '*') {
                    cur[j] = prev[j] || cur[j - 1];
                } else if (p.charAt(j - 1) == '?' || s.charAt(i - 1) == p.charAt(j - 1)) {
                    cur[j] = prev[j - 1];
                } else {
                    cur[j] = false;
                }
            }
            
            prev = cur.clone();
        }
        
        return prev[m];
    }
}
```

### 36. String DP Problems

```java
// Regular Expression Matching
public class RegexMatching {
    public static boolean isMatch(String s, String p) {
        int m = s.length();
        int n = p.length();
        boolean[][] dp = new boolean[m + 1][n + 1];
        
        dp[0][0] = true;
        
        for (int j = 2; j <= n; j += 2) {
            if (p.charAt(j - 1) == '*') {
                dp[0][j] = dp[0][j - 2];
            }
        }
        
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (p.charAt(j - 1) == '*') {
                    dp[i][j] = dp[i][j - 2] || 
                              (dp[i - 1][j] && (s.charAt(i - 1) == p.charAt(j - 2) || p.charAt(j - 2) == '.'));
                } else {
                    dp[i][j] = dp[i - 1][j - 1] && 
                              (s.charAt(i - 1) == p.charAt(j - 1) || p.charAt(j - 1) == '.');
                }
            }
        }
        
        return dp[m][n];
    }
}
```

### 37. Best Time to Buy and Sell Stock
**Time:** O(n) **Space:** O(1)

```java
public class BestTimeToBuyAndSellStock {
    public static int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;
        
        for (int price : prices) {
            if (price < minPrice) {
                minPrice = price;
            } else if (price - minPrice > maxProfit) {
                maxProfit = price - minPrice;
            }
        }
        
        return maxProfit;
    }
}
```

### 38. Best Time to Buy and Sell Stock II
**Time:** O(n) **Space:** O(n) / O(1)

```java
public class BestTimeToBuyAndSellStockII {
    public static int maxProfit(int[] prices) {
        int n = prices.length;
        int[][] dp = new int[n + 1][2];
        
        dp[n][0] = dp[n][1] = 0;
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                int profit = 0;
                
                if (buy == 0) {
                    profit = Math.max(0 + dp[ind + 1][0], -prices[ind] + dp[ind + 1][1]);
                }
                
                if (buy == 1) {
                    profit = Math.max(0 + dp[ind + 1][1], prices[ind] + dp[ind + 1][0]);
                }
                
                dp[ind][buy] = profit;
            }
        }
        
        return dp[0][0];
    }
    
    public static int maxProfitSpaceOptimized(int[] prices) {
        int n = prices.length;
        int[] ahead = new int[2];
        int[] cur = new int[2];
        
        ahead[0] = ahead[1] = 0;
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                int profit = 0;
                
                if (buy == 0) {
                    profit = Math.max(0 + ahead[0], -prices[ind] + ahead[1]);
                }
                
                if (buy == 1) {
                    profit = Math.max(0 + ahead[1], prices[ind] + ahead[0]);
                }
                
                cur[buy] = profit;
            }
            
            ahead = cur.clone();
        }
        
        return ahead[0];
    }
    
    public static int maxProfitGreedy(int[] prices) {
        int maxProfit = 0;
        
        for (int i = 1; i < prices.length; i++) {
            if (prices[i] > prices[i - 1]) {
                maxProfit += prices[i] - prices[i - 1];
            }
        }
        
        return maxProfit;
    }
}
```

### 39. Best Time to Buy and Sell Stock III
**Time:** O(n) **Space:** O(n) / O(1)

```java
public class BestTimeToBuyAndSellStockIII {
    public static int maxProfit(int[] prices) {
        int n = prices.length;
        int[][][] dp = new int[n + 1][2][3];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                for (int cap = 1; cap <= 2; cap++) {
                    if (buy == 0) {
                        dp[ind][buy][cap] = Math.max(0 + dp[ind + 1][0][cap], 
                                                    -prices[ind] + dp[ind + 1][1][cap]);
                    }
                    
                    if (buy == 1) {
                        dp[ind][buy][cap] = Math.max(0 + dp[ind + 1][1][cap], 
                                                    prices[ind] + dp[ind + 1][0][cap - 1]);
                    }
                }
            }
        }
        
        return dp[0][0][2];
    }
    
    public static int maxProfitSpaceOptimized(int[] prices) {
        int n = prices.length;
        int[][] ahead = new int[2][3];
        int[][] cur = new int[2][3];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                for (int cap = 1; cap <= 2; cap++) {
                    if (buy == 0) {
                        cur[buy][cap] = Math.max(0 + ahead[0][cap], 
                                               -prices[ind] + ahead[1][cap]);
                    }
                    
                    if (buy == 1) {
                        cur[buy][cap] = Math.max(0 + ahead[1][cap], 
                                               prices[ind] + ahead[0][cap - 1]);
                    }
                }
            }
            
            for (int i = 0; i < 2; i++) {
                for (int j = 0; j < 3; j++) {
                    ahead[i][j] = cur[i][j];
                }
            }
        }
        
        return ahead[0][2];
    }
}
```

### 40. Best Time to Buy and Sell Stock IV
**Time:** O(n × k) **Space:** O(n × k) / O(k)

```java
public class BestTimeToBuyAndSellStockIV {
    public static int maxProfit(int k, int[] prices) {
        int n = prices.length;
        
        if (n <= 0 || k <= 0) return 0;
        
        if (2 * k > n) {
            int res = 0;
            for (int i = 1; i < n; i++) {
                res += Math.max(0, prices[i] - prices[i - 1]);
            }
            return res;
        }
        
        int[][][] dp = new int[n + 1][2][k + 1];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                for (int cap = 1; cap <= k; cap++) {
                    if (buy == 0) {
                        dp[ind][buy][cap] = Math.max(0 + dp[ind + 1][0][cap], 
                                                    -prices[ind] + dp[ind + 1][1][cap]);
                    }
                    
                    if (buy == 1) {
                        dp[ind][buy][cap] = Math.max(0 + dp[ind + 1][1][cap], 
                                                    prices[ind] + dp[ind + 1][0][cap - 1]);
                    }
                }
            }
        }
        
        return dp[0][0][k];
    }
    
    public static int maxProfitSpaceOptimized(int k, int[] prices) {
        int n = prices.length;
        
        if (n <= 0 || k <= 0) return 0;
        
        if (2 * k > n) {
            int res = 0;
            for (int i = 1; i < n; i++) {
                res += Math.max(0, prices[i] - prices[i - 1]);
            }
            return res;
        }
        
        int[][] ahead = new int[2][k + 1];
        int[][] cur = new int[2][k + 1];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                for (int cap = 1; cap <= k; cap++) {
                    if (buy == 0) {
                        cur[buy][cap] = Math.max(0 + ahead[0][cap], 
                                               -prices[ind] + ahead[1][cap]);
                    }
                    
                    if (buy == 1) {
                        cur[buy][cap] = Math.max(0 + ahead[1][cap], 
                                               prices[ind] + ahead[0][cap - 1]);
                    }
                }
            }
            
            ahead = cur;
            cur = new int[2][k + 1];
        }
        
        return ahead[0][k];
    }
}
```

### 41. Best Time to Buy and Sell Stock with Cooldown
**Time:** O(n) **Space:** O(n) / O(1)

```java
public class BestTimeToBuyAndSellStockWithCooldown {
    public static int maxProfit(int[] prices) {
        int n = prices.length;
        int[][] dp = new int[n + 2][2];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                int profit = 0;
                
                if (buy == 0) {
                    profit = Math.max(0 + dp[ind + 1][0], -prices[ind] + dp[ind + 1][1]);
                }
                
                if (buy == 1) {
                    profit = Math.max(0 + dp[ind + 1][1], prices[ind] + dp[ind + 2][0]);
                }
                
                dp[ind][buy] = profit;
            }
        }
        
        return dp[0][0];
    }
    
    public static int maxProfitSpaceOptimized(int[] prices) {
        int n = prices.length;
        int[] front2 = new int[2];
        int[] front1 = new int[2];
        int[] cur = new int[2];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            cur[0] = Math.max(0 + front1[0], -prices[ind] + front1[1]);
            cur[1] = Math.max(0 + front1[1], prices[ind] + front2[0]);
            
            front2 = front1.clone();
            front1 = cur.clone();
        }
        
        return cur[0];
    }
}
```

### 42. Best Time to Buy and Sell Stock with Transaction Fee
**Time:** O(n) **Space:** O(n) / O(1)

```java
public class BestTimeToBuyAndSellStockWithFee {
    public static int maxProfit(int[] prices, int fee) {
        int n = prices.length;
        int[][] dp = new int[n + 1][2];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                int profit = 0;
                
                if (buy == 0) {
                    profit = Math.max(0 + dp[ind + 1][0], -prices[ind] + dp[ind + 1][1]);
                }
                
                if (buy == 1) {
                    profit = Math.max(0 + dp[ind + 1][1], prices[ind] - fee + dp[ind + 1][0]);
                }
                
                dp[ind][buy] = profit;
            }
        }
        
        return dp[0][0];
    }
    
    public static int maxProfitSpaceOptimized(int[] prices, int fee) {
        int n = prices.length;
        int[] ahead = new int[2];
        int[] cur = new int[2];
        
        for (int ind = n - 1; ind >= 0; ind--) {
            cur[0] = Math.max(0 + ahead[0], -prices[ind] + ahead[1]);
            cur[1] = Math.max(0 + ahead[1], prices[ind] - fee + ahead[0]);
            
            ahead = cur.clone();
        }
        
        return ahead[0];
    }
}
```

### 43. Longest Increasing Subsequence
**Time:** O(n²) / O(n log n) **Space:** O(n)

```java
import java.util.*;

public class LongestIncreasingSubsequence {
    public static int lengthOfLIS(int[] nums) {
        int n = nums.length;
        int[] dp = new int[n];
        Arrays.fill(dp, 1);
        
        for (int i = 0; i <= n - 1; i++) {
            for (int prev_index = 0; prev_index <= i - 1; prev_index++) {
                if (nums[prev_index] < nums[i]) {
                    dp[i] = Math.max(dp[i], 1 + dp[prev_index]);
                }
            }
        }
        
        int ans = -1;
        for (int i = 0; i <= n - 1; i++) {
            ans = Math.max(ans, dp[i]);
        }
        
        return ans;
    }
    
    public static int lengthOfLISBinarySearch(int[] nums) {
        List<Integer> temp = new ArrayList<>();
        temp.add(nums[0]);
        
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > temp.get(temp.size() - 1)) {
                temp.add(nums[i]);
            } else {
                int ind = Collections.binarySearch(temp, nums[i]);
                if (ind < 0) {
                    ind = -ind - 1;
                }
                temp.set(ind, nums[i]);
            }
        }
        
        return temp.size();
    }
    
    public static void printLIS(int[] nums) {
        int n = nums.length;
        int[] dp = new int[n];
        int[] hash = new int[n];
        Arrays.fill(dp, 1);
        
        for (int i = 0; i <= n - 1; i++) {
            hash[i] = i;
            for (int prev_index = 0; prev_index <= i - 1; prev_index++) {
                if (nums[prev_index] < nums[i] && 1 + dp[prev_index] > dp[i]) {
                    dp[i] = 1 + dp[prev_index];
                    hash[i] = prev_index;
                }
            }
        }
        
        int ans = -1;
        int lastIndex = -1;
        
        for (int i = 0; i <= n - 1; i++) {
            if (dp[i] > ans) {
                ans = dp[i];
                lastIndex = i;
            }
        }
        
        List<Integer> temp = new ArrayList<>();
        temp.add(nums[lastIndex]);
        
        while (hash[lastIndex] != lastIndex) {
            lastIndex = hash[lastIndex];
            temp.add(nums[lastIndex]);
        }
        
        Collections.reverse(temp);
        
        for (int num : temp) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```

---


## Tries

### Trie Node Structure

```java
class TrieNode {
    TrieNode[] children;
    boolean isEndOfWord;
    
    public TrieNode() {
        children = new TrieNode[26];
        isEndOfWord = false;
    }
}

class TrieNodeAdvanced {
    TrieNodeAdvanced[] children;
    int countEndsWith;
    int countPrefix;
    
    public TrieNodeAdvanced() {
        children = new TrieNodeAdvanced[26];
        countEndsWith = 0;
        countPrefix = 0;
    }
}
```

### 1. Implement Trie I (Insert, Search, StartsWith)
**Time:** O(L) per operation **Space:** O(ALPHABET_SIZE × N × M)

```java
public class Trie {
    private TrieNode root;
    
    public Trie() {
        root = new TrieNode();
    }
    
    public void insert(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                node.children[index] = new TrieNode();
            }
            node = node.children[index];
        }
        node.isEndOfWord = true;
    }
    
    public boolean search(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                return false;
            }
            node = node.children[index];
        }
        return node.isEndOfWord;
    }
    
    public boolean startsWith(String prefix) {
        TrieNode node = root;
        for (char c : prefix.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                return false;
            }
            node = node.children[index];
        }
        return true;
    }
}
```

### 2. Implement Trie II (Insert, CountWordsEqualTo, CountWordsStartingWith, Erase)
**Time:** O(L) per operation **Space:** O(ALPHABET_SIZE × N × M)

```java
public class TrieII {
    private TrieNodeAdvanced root;
    
    public TrieII() {
        root = new TrieNodeAdvanced();
    }
    
    public void insert(String word) {
        TrieNodeAdvanced node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                node.children[index] = new TrieNodeAdvanced();
            }
            node = node.children[index];
            node.countPrefix++;
        }
        node.countEndsWith++;
    }
    
    public int countWordsEqualTo(String word) {
        TrieNodeAdvanced node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                return 0;
            }
            node = node.children[index];
        }
        return node.countEndsWith;
    }
    
    public int countWordsStartingWith(String prefix) {
        TrieNodeAdvanced node = root;
        for (char c : prefix.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                return 0;
            }
            node = node.children[index];
        }
        return node.countPrefix;
    }
    
    public void erase(String word) {
        TrieNodeAdvanced node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            node = node.children[index];
            node.countPrefix--;
        }
        node.countEndsWith--;
    }
}
```

### 3. Longest Word with All Prefixes (Complete String)
**Time:** O(N × L) **Space:** O(N × L)

```java
public class LongestWordWithAllPrefixes {
    private TrieNode root;
    
    public LongestWordWithAllPrefixes() {
        root = new TrieNode();
    }
    
    private void insert(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                node.children[index] = new TrieNode();
            }
            node = node.children[index];
        }
        node.isEndOfWord = true;
    }
    
    private boolean checkAllPrefixExist(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            node = node.children[index];
            if (!node.isEndOfWord) {
                return false;
            }
        }
        return true;
    }
    
    public String longestCompleteString(String[] words) {
        for (String word : words) {
            insert(word);
        }
        
        String longest = "";
        
        for (String word : words) {
            if (checkAllPrefixExist(word)) {
                if (word.length() > longest.length() || 
                    (word.length() == longest.length() && word.compareTo(longest) < 0)) {
                    longest = word;
                }
            }
        }
        
        return longest.isEmpty() ? "None" : longest;
    }
}
```

### 4. Number of Distinct Substrings Using Trie
**Time:** O(N²) **Space:** O(N²)

```java
public class DistinctSubstrings {
    private TrieNode root;
    
    public DistinctSubstrings() {
        root = new TrieNode();
    }
    
    private int insertAndCount(String s) {
        int count = 0;
        
        for (int i = 0; i < s.length(); i++) {
            TrieNode node = root;
            
            for (int j = i; j < s.length(); j++) {
                int index = s.charAt(j) - 'a';
                
                if (node.children[index] == null) {
                    node.children[index] = new TrieNode();
                    count++;
                }
                
                node = node.children[index];
            }
        }
        
        return count;
    }
    
    public int countDistinctSubstrings(String s) {
        return insertAndCount(s) + 1;
    }
}
```

### 5. Maximum XOR of Two Numbers in Array
**Time:** O(32 × N) **Space:** O(32 × N)

```java
public class MaximumXOR {
    static class TrieNodeBinary {
        TrieNodeBinary[] children;
        
        public TrieNodeBinary() {
            children = new TrieNodeBinary[2];
        }
    }
    
    private TrieNodeBinary root;
    
    public MaximumXOR() {
        root = new TrieNodeBinary();
    }
    
    private void insert(int num) {
        TrieNodeBinary node = root;
        
        for (int i = 31; i >= 0; i--) {
            int bit = (num >> i) & 1;
            
            if (node.children[bit] == null) {
                node.children[bit] = new TrieNodeBinary();
            }
            
            node = node.children[bit];
        }
    }
    
    private int getMaxXOR(int num) {
        TrieNodeBinary node = root;
        int maxXOR = 0;
        
        for (int i = 31; i >= 0; i--) {
            int bit = (num >> i) & 1;
            
            if (node.children[1 - bit] != null) {
                maxXOR = maxXOR | (1 << i);
                node = node.children[1 - bit];
            } else {
                node = node.children[bit];
            }
        }
        
        return maxXOR;
    }
    
    public int findMaximumXOR(int[] nums) {
        for (int num : nums) {
            insert(num);
        }
        
        int maxXOR = 0;
        for (int num : nums) {
            maxXOR = Math.max(maxXOR, getMaxXOR(num));
        }
        
        return maxXOR;
    }
}
```

### 6. Maximum XOR Subarray (Max XOR with Given K)
**Time:** O(Q × 32 × N) **Space:** O(32 × N)

```java
import java.util.*;

public class MaximumXORSubarray {
    static class TrieNodeBinary {
        TrieNodeBinary[] children;
        
        public TrieNodeBinary() {
            children = new TrieNodeBinary[2];
        }
    }
    
    private TrieNodeBinary root;
    
    public MaximumXORSubarray() {
        root = new TrieNodeBinary();
    }
    
    private void insert(int num) {
        TrieNodeBinary node = root;
        
        for (int i = 31; i >= 0; i--) {
            int bit = (num >> i) & 1;
            
            if (node.children[bit] == null) {
                node.children[bit] = new TrieNodeBinary();
            }
            
            node = node.children[bit];
        }
    }
    
    private int getMaxXOR(int num) {
        TrieNodeBinary node = root;
        int maxXOR = 0;
        
        for (int i = 31; i >= 0; i--) {
            int bit = (num >> i) & 1;
            
            if (node.children[1 - bit] != null) {
                maxXOR = maxXOR | (1 << i);
                node = node.children[1 - bit];
            } else {
                node = node.children[bit];
            }
        }
        
        return maxXOR;
    }
    
    public int[] maximizeXOR(int[] nums, int[][] queries) {
        Arrays.sort(nums);
        
        int[][] queriesWithIndex = new int[queries.length][3];
        for (int i = 0; i < queries.length; i++) {
            queriesWithIndex[i][0] = queries[i][0];
            queriesWithIndex[i][1] = queries[i][1];
            queriesWithIndex[i][2] = i;
        }
        
        Arrays.sort(queriesWithIndex, (a, b) -> a[1] - b[1]);
        
        int[] result = new int[queries.length];
        int index = 0;
        
        root = new TrieNodeBinary();
        
        for (int[] query : queriesWithIndex) {
            int x = query[0];
            int m = query[1];
            int queryIndex = query[2];
            
            while (index < nums.length && nums[index] <= m) {
                insert(nums[index]);
                index++;
            }
            
            if (index == 0) {
                result[queryIndex] = -1;
            } else {
                result[queryIndex] = getMaxXOR(x);
            }
        }
        
        return result;
    }
}
```

### 7. Power Set Using Trie
**Time:** O(2^N × N) **Space:** O(2^N × N)

```java
import java.util.*;

public class PowerSetTrie {
    private TrieNode root;
    
    public PowerSetTrie() {
        root = new TrieNode();
    }
    
    static class TrieNode {
        Map<Character, TrieNode> children;
        boolean isEndOfSubset;
        
        public TrieNode() {
            children = new HashMap<>();
            isEndOfSubset = false;
        }
    }
    
    private void insert(String subset) {
        TrieNode node = root;
        
        for (char c : subset.toCharArray()) {
            node.children.putIfAbsent(c, new TrieNode());
            node = node.children.get(c);
        }
        
        node.isEndOfSubset = true;
    }
    
    private void generateAllSubsets(int[] nums, int index, StringBuilder current, List<String> result) {
        if (index == nums.length) {
            String subset = current.toString();
            insert(subset);
            result.add(subset);
            return;
        }
        
        generateAllSubsets(nums, index + 1, current, result);
        
        current.append(nums[index]).append(",");
        generateAllSubsets(nums, index + 1, current, result);
        current.setLength(current.length() - String.valueOf(nums[index]).length() - 1);
    }
    
    public List<String> powerSet(int[] nums) {
        List<String> result = new ArrayList<>();
        generateAllSubsets(nums, 0, new StringBuilder(), result);
        return result;
    }
    
    private void getAllSubsets(TrieNode node, StringBuilder current, List<String> result) {
        if (node.isEndOfSubset) {
            result.add(current.toString());
        }
        
        for (Map.Entry<Character, TrieNode> entry : node.children.entrySet()) {
            current.append(entry.getKey());
            getAllSubsets(entry.getValue(), current, result);
            current.setLength(current.length() - 1);
        }
    }
    
    public List<String> getAllSubsetsFromTrie() {
        List<String> result = new ArrayList<>();
        getAllSubsets(root, new StringBuilder(), result);
        return result;
    }
}
```

### Auto-Complete System
**Time:** O(L) insert, O(L + K) search **Space:** O(ALPHABET_SIZE × N × M)

```java
import java.util.*;

public class AutoCompleteSystem {
    static class TrieNodeAuto {
        Map<Character, TrieNodeAuto> children;
        Map<String, Integer> sentences;
        
        public TrieNodeAuto() {
            children = new HashMap<>();
            sentences = new HashMap<>();
        }
    }
    
    private TrieNodeAuto root;
    private StringBuilder currentInput;
    
    public AutoCompleteSystem(String[] sentences, int[] times) {
        root = new TrieNodeAuto();
        currentInput = new StringBuilder();
        
        for (int i = 0; i < sentences.length; i++) {
            insert(sentences[i], times[i]);
        }
    }
    
    private void insert(String sentence, int time) {
        TrieNodeAuto node = root;
        
        for (char c : sentence.toCharArray()) {
            node.children.putIfAbsent(c, new TrieNodeAuto());
            node = node.children.get(c);
            node.sentences.put(sentence, node.sentences.getOrDefault(sentence, 0) + time);
        }
    }
    
    public List<String> input(char c) {
        if (c == '#') {
            String sentence = currentInput.toString();
            insert(sentence, 1);
            currentInput.setLength(0);
            return new ArrayList<>();
        }
        
        currentInput.append(c);
        String prefix = currentInput.toString();
        
        TrieNodeAuto node = root;
        for (char ch : prefix.toCharArray()) {
            if (!node.children.containsKey(ch)) {
                return new ArrayList<>();
            }
            node = node.children.get(ch);
        }
        
        PriorityQueue<Map.Entry<String, Integer>> pq = new PriorityQueue<>((a, b) -> {
            if (a.getValue() != b.getValue()) {
                return a.getValue() - b.getValue();
            }
            return b.getKey().compareTo(a.getKey());
        });
        
        for (Map.Entry<String, Integer> entry : node.sentences.entrySet()) {
            pq.offer(entry);
            if (pq.size() > 3) {
                pq.poll();
            }
        }
        
        List<String> result = new ArrayList<>();
        while (!pq.isEmpty()) {
            result.add(0, pq.poll().getKey());
        }
        
        return result;
    }
}
```

### Word Search II
**Time:** O(M × N × 4^L) **Space:** O(K × L)

```java
import java.util.*;

public class WordSearchII {
    static class TrieNodeSearch {
        TrieNodeSearch[] children;
        String word;
        
        public TrieNodeSearch() {
            children = new TrieNodeSearch[26];
        }
    }
    
    private TrieNodeSearch root;
    private List<String> result;
    private int[][] directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
    
    public List<String> findWords(char[][] board, String[] words) {
        root = new TrieNodeSearch();
        result = new ArrayList<>();
        
        for (String word : words) {
            insert(word);
        }
        
        int m = board.length;
        int n = board[0].length;
        
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                dfs(board, i, j, root);
            }
        }
        
        return result;
    }
    
    private void insert(String word) {
        TrieNodeSearch node = root;
        
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                node.children[index] = new TrieNodeSearch();
            }
            node = node.children[index];
        }
        
        node.word = word;
    }
    
    private void dfs(char[][] board, int i, int j, TrieNodeSearch node) {
        if (i < 0 || i >= board.length || j < 0 || j >= board[0].length) {
            return;
        }
        
        char c = board[i][j];
        if (c == '*' || node.children[c - 'a'] == null) {
            return;
        }
        
        node = node.children[c - 'a'];
        
        if (node.word != null) {
            result.add(node.word);
            node.word = null;
        }
        
        board[i][j] = '*';
        
        for (int[] dir : directions) {
            dfs(board, i + dir[0], j + dir[1], node);
        }
        
        board[i][j] = c;
    }
}
```

### Replace Words
**Time:** O(N × L + M × K) **Space:** O(N × L)

```java
import java.util.*;

public class ReplaceWords {
    static class TrieNodeReplace {
        TrieNodeReplace[] children;
        String word;
        
        public TrieNodeReplace() {
            children = new TrieNodeReplace[26];
        }
    }
    
    private TrieNodeReplace root;
    
    public ReplaceWords() {
        root = new TrieNodeReplace();
    }
    
    private void insert(String word) {
        TrieNodeReplace node = root;
        
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                node.children[index] = new TrieNodeReplace();
            }
            node = node.children[index];
        }
        
        node.word = word;
    }
    
    private String searchRoot(String word) {
        TrieNodeReplace node = root;
        
        for (char c : word.toCharArray()) {
            int index = c - 'a';
            if (node.children[index] == null) {
                break;
            }
            node = node.children[index];
            if (node.word != null) {
                return node.word;
            }
        }
        
        return word;
    }
    
    public String replaceWords(List<String> dictionary, String sentence) {
        for (String root : dictionary) {
            insert(root);
        }
        
        String[] words = sentence.split(" ");
        StringBuilder result = new StringBuilder();
        
        for (int i = 0; i < words.length; i++) {
            if (i > 0) result.append(" ");
            result.append(searchRoot(words[i]));
        }
        
        return result.toString();
    }
}
```

---

