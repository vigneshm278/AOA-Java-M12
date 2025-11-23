
# EX 2B Jump Game using Greedy Algorithm.
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Start the program and import the `Scanner` class to take user input.  
2. Read the size of the array `n` and input the array elements.  
3. Initialize a variable `maxReach` to track the farthest index that can be reached.  
4. Iterate through the array, updating `maxReach` and checking if the current index exceeds it.  
5. If traversal completes without exceeding `maxReach`, print that the last index can be reached; otherwise, print false.

## Program:
```
/*
Program to implement Reverse a String

# EX 2A Assign Cookies using Greedy Algorithm. 
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Start the program and import the `Scanner` and `Arrays` classes.
2. Read the number of children `n` and their greed factors into array `g`.
3. Read the number of cookies `m` and their sizes into array `s`.
4. Sort both arrays and use two pointers to compare greed and cookie size.
5. Count and display the maximum number of children who can be content with the available cookies.


## Program:
```
/*
Program to implement Reverse a String
Developed by: Vignesh M
Register Number: 212223240176
*/
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        // Type Your Logic Here.
        Arrays.sort(g);
        Arrays.sort(s);
        int i = 0, j = 0, count = 0;
        while (i < g.length && j < s.length) {
            if (s[j] >= g[i]) {
                count++;
                i++;
                j++;
            } else {
                j++;
            }
        }
        return count;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}

```

## Output:
<img width="588" height="319" alt="image" src="https://github.com/user-attachments/assets/ff26a77b-4298-43fd-8321-cdc42c6c947e" />



## Result:
The program successfully implemented and the expected output is verified.

*/
import java.util.Scanner;

public class JumpGame {

    // Function to check if we can reach the last index
    public static boolean canReachLastIndex(int[] nums) {
        // Type Your Code Here.
        int maxReach = 0;
    for (int i = 0; i < nums.length; i++) {
        if (i > maxReach) return false;
        maxReach = Math.max(maxReach, i + nums[i]);
    }
    return true;
    }

    // Main method for input and calling the function
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Size of array
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt(); // Elements of array
        }

        System.out.println("Can reach last index: " + canReachLastIndex(nums));
    }
}

```

## Output:

<img width="749" height="226" alt="image" src="https://github.com/user-attachments/assets/c9c578f9-918a-4bb3-a4ee-c2d14d22a5e4" />


## Result:
The program successfully implemented and the expected output is verified.
