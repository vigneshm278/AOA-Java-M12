
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




# EX 2C Job Sequencing using Greedy Approach
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm

1. Start the program and import the `Scanner` and `Arrays` classes.
2. Read the number of jobs `n` and input each job’s `id`, `deadline`, and `profit`.
3. Sort all jobs in descending order based on profit to prioritize high-profit jobs.
4. Assign jobs to available slots before their deadlines, ensuring only one job per time slot.
5. Count the total scheduled jobs and sum up their profits, then display both values as output.
 

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vignesh M
Register Number: 212223240176
*/

import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        // Type Your Code Here.
        Arrays.sort(jobs, (a, b) -> b.profit - a.profit);

    int maxDeadline = 0;
    for (Job job : jobs) {
        if (job.deadline > maxDeadline)
            maxDeadline = job.deadline;
    }

    int[] slot = new int[maxDeadline + 1];
    Arrays.fill(slot, -1);

    int countJobs = 0, jobProfit = 0;

    for (int i = 0; i < n; i++) {
        for (int j = jobs[i].deadline; j > 0; j--) {
            if (slot[j] == -1) {
                slot[j] = jobs[i].id;
                countJobs++;
                jobProfit += jobs[i].profit;
                break;
            }
        }
    }

    return new int[]{countJobs, jobProfit};
        
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}

```

## Output:
<img width="563" height="403" alt="image" src="https://github.com/user-attachments/assets/b4254006-7acc-4300-92b5-7903a852dda6" />



## Result:
The program successfully implemented and the expected output is verified.



# EX 2D Pattern Matching using Naive Approach.
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12
## Algorithm

1. Start the program and import the `Scanner` class to take input.
2. Read the text string and the pattern string from the user.
3. Calculate the lengths of both the text and the pattern.
4. Slide the pattern over the text one character at a time and compare each substring with the pattern.
5. Print the starting index each time the pattern matches completely within the text.


## Program:
```
/*
Program to implement Reverse a String
Developed by: Vignesh M
Register Number: 212223240176
*/
import java.util.Scanner;

public class NaivePatternSearch {
    //Type code here....
    public static void search(String text,String pattern)
    {
        int n=text.length();
        int m=pattern.length();
        for(int i=0;i<=n-m;i++)
        {
            int j;
            for(j=0;j<m;j++)
            {
                if(text.charAt(i+j) !=pattern.charAt(j))
                {
                    break;
                }
            }
            if(j==m)
            {
                System.out.println("Pattern found at index "+i);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input from the user
        String text = scanner.nextLine();
        String pattern = scanner.nextLine();

        // Search for pattern in the text
        search(text, pattern);

        scanner.close();
    }
}
```

## Output:
<img width="747" height="210" alt="image" src="https://github.com/user-attachments/assets/2723b9f0-d5c2-4eb3-8fa0-52bc6a70043d" />




## Result:
The program successfully implemented and the expected output is verified.



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





