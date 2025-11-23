
# EX 2E Pattern Matching using KMP Algorithm.
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm:

1. Start the program and import the required Java utility classes.
2. Read the number of test cases `T` from the user.
3. For each test case, input the text string and the pattern string.
4. Use a loop to slide the pattern over the text and compare each substring with the pattern.
5. Store all matching starting indices in a list and print them; if no match is found, print `-1`.


## Program:
```
/*
Program to implement Reverse a String
Developed by: Vignesh M
Register Number: 212223240176
*/
import java.util.*;

public class PatternMatching {
//type your code
    public static List<Integer> findPatternIndices(String text, String pattern) {
        List<Integer> result = new ArrayList<>();
        int n = text.length();
        int m = pattern.length();

        // Only check up to n - m
        for (int i = 0; i <= n - m; i++) {
            int j;
            for (j = 0; j < m; j++) {
                if (text.charAt(i + j) != pattern.charAt(j)) {
                    break;
                }
            }
            if (j == m) { // pattern matched
                result.add(i);
            }
        }

        // If no matches, return [-1]
        if (result.isEmpty()) {
            result.add(-1);
        }

        return result;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int T = Integer.parseInt(scanner.nextLine()); // number of test cases

        for (int t = 0; t < T; t++) {
            String text = scanner.nextLine();
            String pattern = scanner.nextLine();

            List<Integer> indices = findPatternIndices(text, pattern);
            for (int idx : indices) {
                System.out.print(idx + " ");
            }
            System.out.println();
        }

        scanner.close();
    }
}
```

## Output:
<img width="665" height="275" alt="image" src="https://github.com/user-attachments/assets/74fd8468-ae1a-4b81-8d17-5fa631a12c29" />



## Result:
The program successfully implemented and the expected output is verified.
