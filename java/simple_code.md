# Top SDET Java Programs for Interview

## Table of Contents

### Numbers
1. [Find odd or even number](#1-find-odd-or-even-number)
2. [Find prime number](#2-find-prime-number)
3. [Fibonacci series up to N terms](#3-fibonacci-series-up-to-n-terms)
4. [Swap two numbers without third variable](#4-swap-two-numbers-without-third-variable)
5. [Factorial of a number](#5-factorial-of-a-number)
6. [Reverse a number](#6-reverse-a-number)
7. [Check Armstrong number](#7-check-armstrong-number)
8. [Count digits in a number](#8-count-digits-in-a-number)
9. [Check palindrome number](#9-check-palindrome-number)
10. [Sum of digits](#10-sum-of-digits)

### Strings
1. [Reverse a string](#1-reverse-a-string-1)
2. [Reverse each word in a string](#2-reverse-each-word-in-a-string)
3. [Find duplicate characters in string](#3-find-duplicate-characters-in-string)
4. [Count occurrences of each word](#4-count-occurrences-of-each-word)
5. [Count words in a string](#5-count-words-in-a-string)
6. [Find all permutations of a string](#6-find-all-permutations-of-a-string)
7. [Check palindrome string](#7-check-palindrome-string)
8. [Check if two strings are anagrams](#8-check-if-two-strings-are-anagrams)
9. [Count vowels and consonants](#9-count-vowels-and-consonants)
10. [Print unique characters](#10-print-unique-characters)
11. [Print even-indexed characters](#11-print-even-indexed-characters)
12. [Remove spaces from string](#12-remove-spaces-from-string)
13. [Print each letter twice](#13-print-each-letter-twice)
14. [Swap two strings without third variable](#14-swap-two-strings-without-third-variable)
15. [Convert `aabbcccdd` to `a2b2c3d2`](#15-convert-aabbcccdd-to-a2b2c3d2)
16. [Separate lowercase and uppercase output](#16-separate-lowercase-and-uppercase-output)
17. [Separate alphabets and numbers](#17-separate-alphabets-and-numbers)
18. [Move all zeros to the end](#18-move-all-zeros-to-the-end)
19. [Move all zeros to the beginning](#19-move-all-zeros-to-the-beginning)
20. [Longest substring without repeating characters](#20-longest-substring-without-repeating-characters)

### Arrays
1. [Find common elements between two arrays](#1-find-common-elements-between-two-arrays-1)
2. [Find first and last element of ArrayList](#2-find-first-and-last-element-of-arraylist)
3. [Sort array without in-built sort](#3-sort-array-without-in-built-sort)
4. [Remove duplicates from an array](#4-remove-duplicates-from-an-array)
5. [Remove duplicates from an ArrayList](#5-remove-duplicates-from-an-arraylist)
6. [Find missing number in array](#6-find-missing-number-in-array)
7. [Find largest and smallest element](#7-find-largest-and-smallest-element)
8. [Search element in array (linear search)](#8-search-element-in-array-linear-search)
9. [Sum only integers from mixed string array](#9-sum-only-integers-from-mixed-string-array)
10. [Find minimum and maximum in array](#10-find-minimum-and-maximum-in-array)
11. [Count odd and even numbers from array](#11-count-odd-and-even-numbers-from-array)
12. [Find non-repeated elements in array](#12-find-non-repeated-elements-in-array)

### OOP
- [Implement `hashCode()` and `equals()`](#implement-hashcode-and-equals)


## Numbers

### 1) Find odd or even number
```java
import java.util.Scanner;

public class OddEven {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter any number: ");
        int number = scanner.nextInt();

        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }
    }
}
```

### 2) Find prime number
```java
import java.util.Scanner;

public class PrimeNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();

        if (isPrime(number)) {
            System.out.println(number + " is a prime number.");
        } else {
            System.out.println(number + " is not a prime number.");
        }
    }

    public static boolean isPrime(int num) {
        if (num <= 1) return false;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }
}
```

### 3) Fibonacci series up to N terms
```java
import java.util.Scanner;

public class FibonacciSeries {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter number of terms: ");
        int number = scanner.nextInt();

        int first = 0, second = 1;
        System.out.print("Fibonacci series: ");
        for (int i = 0; i < number; i++) {
            System.out.print(first + " ");
            int next = first + second;
            first = second;
            second = next;
        }
    }
}
```

### 4) Swap two numbers without third variable
```java
public class SwapNumbers {
    public static void main(String[] args) {
        int a = 5;
        int b = 10;

        System.out.println("Before swapping: a = " + a + ", b = " + b);

        a = a + b;
        b = a - b;
        a = a - b;

        System.out.println("After swapping: a = " + a + ", b = " + b);
    }
}
```

### 5) Factorial of a number
```java
import java.util.Scanner;

public class FactorialNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter any number: ");
        int number = scanner.nextInt();

        long factorial = 1;
        for (int i = 1; i <= number; i++) {
            factorial *= i;
        }

        System.out.println("Factorial is: " + factorial);
    }
}
```

### 6) Reverse a number
```java
import java.util.Scanner;

public class ReverseNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter any number: ");
        int number = scanner.nextInt();

        int reversed = 0;
        while (number > 0) {
            int digit = number % 10;
            reversed = reversed * 10 + digit;
            number = number / 10;
        }

        System.out.println("Reverse: " + reversed);
    }
}
```

### 7) Check Armstrong number
```java
import java.util.Scanner;

public class ArmstrongNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter any number: ");
        int number = scanner.nextInt();

        int original = number;
        int sum = 0;

        while (number > 0) {
            int digit = number % 10;
            sum += digit * digit * digit;
            number /= 10;
        }

        if (sum == original) {
            System.out.println("Armstrong number");
        } else {
            System.out.println("Not Armstrong number");
        }
    }
}
```

### 8) Count digits in a number
```java
import java.util.Scanner;

public class NumberOfDigits {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter any number: ");
        int number = scanner.nextInt();

        if (number == 0) {
            System.out.println("Number of digits: 1");
            return;
        }

        number = Math.abs(number);
        int count = 0;

        while (number > 0) {
            number /= 10;
            count++;
        }

        System.out.println("Number of digits: " + count);
    }
}
```

### 9) Check palindrome number
```java
import java.util.Scanner;

public class PalindromeNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();

        if (isPalindrome(number)) {
            System.out.println(number + " is a palindrome.");
        } else {
            System.out.println(number + " is not a palindrome.");
        }
    }

    public static boolean isPalindrome(int num) {
        int original = num;
        int reversed = 0;

        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }

        return original == reversed;
    }
}
```

### 10) Sum of digits
```java
public class SumOfDigits {
    public static void main(String[] args) {
        int number = 12345;
        int sum = calculateSumOfDigits(number);
        System.out.println("Sum of digits of " + number + " is: " + sum);
    }

    public static int calculateSumOfDigits(int number) {
        int sum = 0;
        while (number > 0) {
            int digit = number % 10;
            sum += digit;
            number = number / 10;
        }
        return sum;
    }
}
```

---

## Strings

### 1) Reverse a string
```java
import java.util.Scanner;

public class ReverseString {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        String reversed = "";
        for (int i = 0; i < input.length(); i++) {
            reversed = input.charAt(i) + reversed;
        }

        System.out.println("Reversed String: " + reversed);
    }
}
```

### 2) Reverse each word in a string
```java
public class ReverseEachWord {
    public static void main(String[] args) {
        reverseEachWordOfString("Java is good programming language");
    }

    static void reverseEachWordOfString(String inputString) {
        String[] words = inputString.split(" ");
        StringBuilder result = new StringBuilder();

        for (String word : words) {
            StringBuilder reversedWord = new StringBuilder(word).reverse();
            result.append(reversedWord).append(" ");
        }

        System.out.println(inputString);
        System.out.println(result.toString().trim());
    }
}
```

### 3) Find duplicate characters in string
```java
import java.util.HashMap;
import java.util.Map;

public class DuplicateCharacters {
    public static void main(String[] args) {
        duplicateCharacterCount("Learn Java Programming");
    }

    static void duplicateCharacterCount(String inputString) {
        Map<Character, Integer> charCountMap = new HashMap<>();

        for (char c : inputString.toCharArray()) {
            charCountMap.put(c, charCountMap.getOrDefault(c, 0) + 1);
        }

        System.out.println("Duplicate Characters in: " + inputString);
        for (Map.Entry<Character, Integer> entry : charCountMap.entrySet()) {
            if (entry.getValue() > 1 && entry.getKey() != ' ') {
                System.out.println(entry.getKey() + " : " + entry.getValue());
            }
        }
    }
}
```

### 4) Count occurrences of each word
```java
import java.util.HashMap;
import java.util.Map;

public class WordCount {
    public static void main(String[] args) {
        characterCount("Test Automation Java Automation");
    }

    static void characterCount(String inputString) {
        Map<String, Integer> countMap = new HashMap<>();

        for (String word : inputString.split("\\s+")) {
            countMap.put(word, countMap.getOrDefault(word, 0) + 1);
        }

        System.out.println("Count map: " + countMap);
    }
}
```

### 5) Count words in a string
```java
import java.util.Scanner;

public class CountWords {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the string: ");
        String s = scanner.nextLine().trim();

        if (s.isEmpty()) {
            System.out.println("Number of words: 0");
        } else {
            int count = s.split("\\s+").length;
            System.out.println("Number of words: " + count);
        }
    }
}
```

### 6) Find all permutations of a string
```java
public class StringPermutations {
    public static void main(String[] args) {
        String str = "abc";
        permute(str, "");
    }

    static void permute(String str, String prefix) {
        if (str.length() == 0) {
            System.out.println(prefix);
            return;
        }

        for (int i = 0; i < str.length(); i++) {
            String rem = str.substring(0, i) + str.substring(i + 1);
            permute(rem, prefix + str.charAt(i));
        }
    }
}
```

### 7) Check palindrome string
```java
public class PalindromeString {
    public static void main(String[] args) {
        String str = "madam";
        System.out.println(isPalindrome(str));
    }

    static boolean isPalindrome(String str) {
        int start = 0;
        int end = str.length() - 1;

        while (start < end) {
            if (str.charAt(start) != str.charAt(end)) {
                return false;
            }
            start++;
            end--;
        }
        return true;
    }
}
```

### 8) Check if two strings are anagrams
```java
public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";

        System.out.println(areAnagrams(str1, str2));
    }

    static boolean areAnagrams(String str1, String str2) {
        if (str1.length() != str2.length()) {
            return false;
        }

        int[] charCount = new int[256];
        for (int i = 0; i < str1.length(); i++) {
            charCount[str1.charAt(i)]++;
            charCount[str2.charAt(i)]--;
        }

        for (int count : charCount) {
            if (count != 0) {
                return false;
            }
        }

        return true;
    }
}
```

### 9) Count vowels and consonants
```java
public class VowelConsonantCount {
    public static void main(String[] args) {
        String str = "Hello World";
        count(str);
    }

    static void count(String str) {
        int vowels = 0;
        int consonants = 0;

        str = str.toLowerCase();

        for (char c : str.toCharArray()) {
            if (c >= 'a' && c <= 'z') {
                if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                    vowels++;
                } else {
                    consonants++;
                }
            }
        }

        System.out.println("Vowels: " + vowels);
        System.out.println("Consonants: " + consonants);
    }
}
```

### 10) Print unique characters
```java
import java.util.Scanner;

public class UniqueCharacters {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        boolean[] seen = new boolean[128];
        System.out.print("Unique characters: ");

        for (int i = 0; i < input.length(); i++) {
            char ch = input.charAt(i);
            if (ch < 128 && !seen[ch]) {
                seen[ch] = true;
                System.out.print(ch + " ");
            }
        }
    }
}
```

### 11) Print even-indexed characters
```java
import java.util.Scanner;

public class EvenIndexedCharacters {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        System.out.print("Even indexed characters: ");
        for (int i = 0; i < input.length(); i += 2) {
            System.out.print(input.charAt(i));
        }
    }
}
```

### 12) Remove spaces from string
```java
import java.util.Scanner;

public class RemoveSpaces {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string with spaces: ");
        String input = scanner.nextLine();

        String withoutSpaces = input.replace(" ", "");
        System.out.println("String without spaces: " + withoutSpaces);
    }
}
```

### 13) Print each letter twice
```java
import java.util.Scanner;

public class DoubleCharacters {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        StringBuilder doubled = new StringBuilder();
        for (char ch : input.toCharArray()) {
            doubled.append(ch).append(ch);
        }

        System.out.println("Doubled characters: " + doubled);
    }
}
```

### 14) Swap two strings without third variable
```java
public class SwapStrings {
    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = "World";

        System.out.println("Before swapping: str1 = " + str1 + ", str2 = " + str2);

        str1 = str1 + str2;
        str2 = str1.substring(0, str1.length() - str2.length());
        str1 = str1.substring(str2.length());

        System.out.println("After swapping: str1 = " + str1 + ", str2 = " + str2);
    }
}
```

### 15) Convert `aabbcccdd` to `a2b2c3d2`
```java
public class CharacterFrequencyRunLength {
    public static void main(String[] args) {
        String input = "aabbcccdd";
        System.out.println(getCharacterCount(input));
    }

    public static String getCharacterCount(String str) {
        if (str == null || str.isEmpty()) return "";

        StringBuilder result = new StringBuilder();
        int count = 1;

        for (int i = 0; i < str.length(); i++) {
            if (i + 1 < str.length() && str.charAt(i) == str.charAt(i + 1)) {
                count++;
            } else {
                result.append(str.charAt(i)).append(count);
                count = 1;
            }
        }

        return result.toString();
    }
}
```

### 16) Separate lowercase and uppercase output
Input: `aBACbcEDed`  
Output lowercase: `abced`  
Output uppercase: `ABCED`

```java
public class SeparateLowerUpper {
    public static void main(String[] args) {
        String input = "aBACbcEDed";
        separateCharacters(input);
    }

    public static void separateCharacters(String input) {
        StringBuilder lowerCase = new StringBuilder();
        StringBuilder upperCase = new StringBuilder();

        for (char ch : input.toCharArray()) {
            if (Character.isLowerCase(ch)) {
                lowerCase.append(ch);
            } else if (Character.isUpperCase(ch)) {
                upperCase.append(ch);
            }
        }

        System.out.println("Output in lowercase: " + lowerCase);
        System.out.println("Output in uppercase: " + upperCase);
    }
}
```

### 17) Separate alphabets and numbers
Input: `Subbu123raj`  
Output alpha: `Subburaj`  
Output numeric: `123`

```java
public class SeparateAlphaNumeric {
    public static void main(String[] args) {
        String input = "Subbu123raj";
        separateAlphaAndNumeric(input);
    }

    public static void separateAlphaAndNumeric(String input) {
        StringBuilder alphaPart = new StringBuilder();
        StringBuilder numericPart = new StringBuilder();

        for (char ch : input.toCharArray()) {
            if (Character.isLetter(ch)) {
                alphaPart.append(ch);
            } else if (Character.isDigit(ch)) {
                numericPart.append(ch);
            }
        }

        System.out.println("Output in Alpha: " + alphaPart);
        System.out.println("Output in Numeric: " + numericPart);
    }
}
```

### 18) Move all zeros to the end
Input: `32400121200`  
Output: `32412120000`

```java
public class MoveZerosToEnd {
    public static void main(String[] args) {
        String input = "32400121200";
        System.out.println(rearrangeDigits(input));
    }

    public static String rearrangeDigits(String input) {
        StringBuilder nonZero = new StringBuilder();
        StringBuilder zero = new StringBuilder();

        for (char c : input.toCharArray()) {
            if (c == '0') {
                zero.append(c);
            } else {
                nonZero.append(c);
            }
        }

        return nonZero.append(zero).toString();
    }
}
```

### 19) Move all zeros to the beginning
Input: `32400121200`  
Output: `00003241212`

```java
public class MoveZerosToStart {
    public static void main(String[] args) {
        String input = "32400121200";
        System.out.println(moveZerosToStart(input));
    }

    public static String moveZerosToStart(String input) {
        StringBuilder zero = new StringBuilder();
        StringBuilder nonZero = new StringBuilder();

        for (char c : input.toCharArray()) {
            if (c == '0') {
                zero.append(c);
            } else {
                nonZero.append(c);
            }
        }

        return zero.append(nonZero).toString();
    }
}
```

### 20) Longest substring without repeating characters
```java
import java.util.HashSet;
import java.util.Set;

public class LongestUniqueSubstring {
    public static void main(String[] args) {
        System.out.println(lengthOfLongestSubstring("abcabcbb")); // 3
        System.out.println(lengthOfLongestSubstring("bbbbb"));    // 1
        System.out.println(lengthOfLongestSubstring("pwwkew"));   // 3
    }

    public static int lengthOfLongestSubstring(String s) {
        Set<Character> set = new HashSet<>();
        int maxLength = 0;
        int start = 0;
        int end = 0;

        while (end < s.length()) {
            char currentChar = s.charAt(end);
            if (!set.contains(currentChar)) {
                set.add(currentChar);
                maxLength = Math.max(maxLength, end - start + 1);
                end++;
            } else {
                set.remove(s.charAt(start));
                start++;
            }
        }

        return maxLength;
    }
}
```

---

## Arrays

### 1) Find common elements between two arrays
```java
import java.util.HashSet;
import java.util.Set;

public class CommonElements {
    public static void main(String[] args) {
        int[] array1 = {1, 2, 3, 4, 5};
        int[] array2 = {4, 5, 6, 7, 8};

        Set<Integer> common = findCommonElements(array1, array2);
        System.out.println("Common elements: " + common);
    }

    public static Set<Integer> findCommonElements(int[] array1, int[] array2) {
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> commonSet = new HashSet<>();

        for (int num : array1) set1.add(num);
        for (int num : array2) {
            if (set1.contains(num)) {
                commonSet.add(num);
            }
        }

        return commonSet;
    }
}
```

### 2) Find first and last element of ArrayList
```java
import java.util.ArrayList;

public class FirstLastArrayList {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");
        list.add("Date");

        if (!list.isEmpty()) {
            System.out.println("First element: " + list.get(0));
            System.out.println("Last element: " + list.get(list.size() - 1));
        } else {
            System.out.println("ArrayList is empty.");
        }
    }
}
```

### 3) Sort array without in-built sort
```java
public class SelectionSortDemo {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 6};
        selectionSort(array);

        for (int num : array) {
            System.out.print(num + " ");
        }
    }

    public static void selectionSort(int[] array) {
        int n = array.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (array[j] < array[minIndex]) {
                    minIndex = j;
                }
            }

            int temp = array[i];
            array[i] = array[minIndex];
            array[minIndex] = temp;
        }
    }
}
```

### 4) Remove duplicates from an array
```java
import java.util.LinkedHashSet;
import java.util.Set;

public class RemoveDuplicatesArray {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 6, 2, 5};
        int[] unique = removeDuplicates(array);

        for (int num : unique) {
            System.out.print(num + " ");
        }
    }

    public static int[] removeDuplicates(int[] array) {
        Set<Integer> set = new LinkedHashSet<>();
        for (int num : array) set.add(num);

        int[] result = new int[set.size()];
        int i = 0;
        for (int num : set) result[i++] = num;

        return result;
    }
}
```

### 5) Remove duplicates from an ArrayList
```java
import java.util.ArrayList;
import java.util.LinkedHashSet;

public class RemoveDuplicatesArrayList {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(5);
        list.add(2);
        list.add(9);
        list.add(1);
        list.add(6);
        list.add(2);
        list.add(5);

        ArrayList<Integer> uniqueList = removeDuplicates(list);
        System.out.println(uniqueList);
    }

    public static ArrayList<Integer> removeDuplicates(ArrayList<Integer> list) {
        return new ArrayList<>(new LinkedHashSet<>(list));
    }
}
```

### 6) Find missing number in array
```java
public class MissingNumber {
    public static void main(String[] args) {
        int[] array = {1, 2, 4, 5, 6};
        System.out.println("Missing number: " + findMissingNumber(array));
    }

    public static int findMissingNumber(int[] array) {
        int n = array.length + 1;
        int totalSum = n * (n + 1) / 2;

        int arraySum = 0;
        for (int num : array) {
            arraySum += num;
        }

        return totalSum - arraySum;
    }
}
```

### 7) Find largest and smallest element
```java
public class LargestSmallest {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 6, 3};
        int[] result = findLargestAndSmallest(array);

        System.out.println("Smallest element: " + result[0]);
        System.out.println("Largest element: " + result[1]);
    }

    public static int[] findLargestAndSmallest(int[] array) {
        if (array == null || array.length == 0) {
            throw new IllegalArgumentException("Array must not be null or empty");
        }

        int smallest = array[0];
        int largest = array[0];

        for (int num : array) {
            if (num < smallest) smallest = num;
            if (num > largest) largest = num;
        }

        return new int[] {smallest, largest};
    }
}
```

### 8) Search element in array (linear search)
```java
public class LinearSearch {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 6, 3};
        int target = 6;

        int index = linearSearch(array, target);
        if (index != -1) {
            System.out.println("Element " + target + " found at index: " + index);
        } else {
            System.out.println("Element " + target + " not found in array.");
        }
    }

    public static int linearSearch(int[] array, int target) {
        for (int i = 0; i < array.length; i++) {
            if (array[i] == target) return i;
        }
        return -1;
    }
}
```

### 9) Sum only integers from mixed string array
```java
public class SumOnlyIntegers {
    public static void main(String[] args) {
        String[] array = {"5", "2", "9", "a", "1", "6", "#", "3"};
        int sum = sumIntegers(array);
        System.out.println("Sum of integers: " + sum);
    }

    public static int sumIntegers(String[] array) {
        int sum = 0;
        for (String element : array) {
            try {
                sum += Integer.parseInt(element);
            } catch (NumberFormatException ignored) {
            }
        }
        return sum;
    }
}
```

### 10) Find minimum and maximum in array
```java
public class MinMax {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 6, 3};

        System.out.println("Minimum: " + findMinimum(array));
        System.out.println("Maximum: " + findMaximum(array));
    }

    public static int findMaximum(int[] array) {
        if (array.length == 0) throw new IllegalArgumentException("Array must not be empty");
        int max = array[0];
        for (int i = 1; i < array.length; i++) {
            if (array[i] > max) max = array[i];
        }
        return max;
    }

    public static int findMinimum(int[] array) {
        if (array.length == 0) throw new IllegalArgumentException("Array must not be empty");
        int min = array[0];
        for (int i = 1; i < array.length; i++) {
            if (array[i] < min) min = array[i];
        }
        return min;
    }
}
```

### 11) Count odd and even numbers from array
```java
public class CountOddEven {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        int[] count = countOddAndEven(array);

        System.out.println("Even numbers count: " + count[1]);
        System.out.println("Odd numbers count: " + count[0]);
    }

    public static int[] countOddAndEven(int[] array) {
        int[] count = new int[2];
        for (int num : array) {
            if (num % 2 == 0) {
                count[1]++;
            } else {
                count[0]++;
            }
        }
        return count;
    }
}
```

### 12) Find non-repeated elements in array
Input: `[1,1,2,2,3,4,5,5,6,6]`  
Output: `[3, 4]`

```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class NonRepeatedElements {
    public static void main(String[] args) {
        int[] array = {1, 1, 2, 2, 3, 4, 5, 5, 6, 6};
        List<Integer> result = findNonRepeatedElements(array);
        System.out.println("Non-repeated elements: " + result);
    }

    public static List<Integer> findNonRepeatedElements(int[] array) {
        Map<Integer, Integer> countMap = new HashMap<>();

        for (int num : array) {
            countMap.put(num, countMap.getOrDefault(num, 0) + 1);
        }

        List<Integer> nonRepeated = new ArrayList<>();
        for (Map.Entry<Integer, Integer> entry : countMap.entrySet()) {
            if (entry.getValue() == 1) {
                nonRepeated.add(entry.getKey());
            }
        }

        return nonRepeated;
    }
}
```

---

## OOP

### Implement `hashCode()` and `equals()`
```java
import java.util.Objects;

public class Student {
    private int id;
    private String name;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, name);
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;

        Student student = (Student) obj;
        return id == student.id && Objects.equals(name, student.name);
    }

    public static void main(String[] args) {
        Student student1 = new Student(1, "Alice");
        Student student2 = new Student(2, "Bob");
        Student student3 = new Student(1, "Alice");

        System.out.println("student1.equals(student2): " + student1.equals(student2));
        System.out.println("student1.equals(student3): " + student1.equals(student3));

        System.out.println("Hashcode of student1: " + student1.hashCode());
        System.out.println("Hashcode of student2: " + student2.hashCode());
        System.out.println("Hashcode of student3: " + student3.hashCode());
    }
}
```
