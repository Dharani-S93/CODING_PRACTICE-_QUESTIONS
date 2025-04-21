

1) Airline's Maintenance System

After every flight, seats with even-numbered seat IDs need to be flagged for special
cleaning due to proximity to air vents. The system receives a list of seat numbers that
were occupied during the flight.

To help the cleaning crew, you must replace every even seat number in the list with 0
to indicate that those seats need to be cleaned.

🔹 Test case 01 :
Input: [2, 4, 6, 8]
Output: [0, 0, 0, 0]

🔹 Test case 02 :
Input: [12, 13, 14]
Output: [0, 13, 0]


### CODE

````JAVA
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        for (int i = 0; i < n; i++) {
            if (a[i] % 2 == 0) {
                a[i] = 0;
            }
        }

        System.out.println(Arrays.toString(a));
    }
}

````
2)Top Two Unique Scores

A teacher wants to reward the top two scoring students in a test. Given the list of
scores, find the two highest unique scores.

Write a function top_two_scores(scores) that returns the two highest unique scores.

🔹 Test Case 01:
Input: [88, 95, 70, 95, 60]
Output: [95, 88]

🔹 Test Case 02:
Input: [85, 85, 85]
Output: [85]

🔹 Test Case 03:
Input: [76]
Output: [76]

🔹 Test Case 04:
Input: [91, 91, 89, 89, 88]
Output: [91, 89]

### CODE
````java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];
        
        for(int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }
        
        Arrays.sort(a);
        
        int temp[] = new int[n];
        int j = 0;
        for(int i = 0; i < n; i++) {
            if(i == 0 || a[i] != a[i-1]) {
                temp[j++] = a[i];
            }
        }
        
        if(j >= 2) {
            System.out.println("[" + temp[j-1] + ", " + temp[j-2] + "]");
        } else if(j == 1) {
            System.out.println("[" + temp[0] + "]");
        } else {
            System.out.println("[]");
        }
    }
}
````

3)Room Rating Tracker

The system tracks the ratings given by students for the condition of their rooms after staying there for a semester. These ratings can be positive (indicating good condition) or negative (indicating poor condition).

The maintenance team needs to focus on rooms with negative ratings. However, the system should not store negative ratings in the database but should instead convert those negative ratings into a positive score to indicate the magnitude of the problem for each room.

🔧 Task:
Write a function `update_room_ratings(ratings)` that takes a list of room ratings and returns a list where all negative ratings are replaced by their squares, while keeping the positive ratings unchanged.

🔹 Test Case 01:
Input:  [1, -4, 2, -8, 5]
Output: [1, 16, 2, 64, 5]

🔹 Test Case 02:
Input:  [0, 5, 10]
Output: [0, 5, 10]

🔹 Test Case 03:
Input:  [-9, -5, -7]
Output: [81, 25, 49]

### CODE
````java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];
        
        for(int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }
        
        for(int i=0;i<n;i++)
        {
            if(a[i]<0)
            {
                a[i]=a[i]*a[i];
            }
        }
        System.out.print(Arrays.toString(a));
    }
}
````
4) Supermarket App: Cart Total Calculator

The person using the supermarket app needs to calculate the total cost of the items in a user's shopping cart after applying some discount rules.

The shopping cart is represented as an array of item prices.

💸 Discount Rules:
1. If the price of an item is greater than 50, a discount of 10% is applied to that item.
2. If the total cost of the cart exceeds 200, an additional 5% discount is applied to the entire cart.

✏️ Task:
Write a function calculate_cart_total(cart) that calculates the final total after applying the discounts.

🔹 Test Case 01:
Input:  [100, 50, 75, 30]
Output: 276.25

🔹 Test Case 02:
Input:  [10, 20, 30, 50]
Output: 110

🔹 Test Case 03:
Input:  [150, 100, 200]
Output: 400

### CODE

````JAVA
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        double a[] = new double[n];
        
        for(int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }
        
        double t = 0;  
        
        for (int i = 0; i < n; i++) {
            if (a[i] > 50) {
                a[i] = a[i] * 0.9; 
            }
            t += a[i];  
        }
                if (t > 200) {
            t *= 0.95;
        }
                System.out.printf("%.2f", t);
    }
}
````
5) You are given two lists of scores for students:

One list contains midterm scores.

The other contains final exam scores.

Each student's final grade is calculated using the following formula:

Midterm score contributes 40%.

Final exam score contributes 60%.

Write a function calculate_final_grades(midterm_scores, final_scores) that calculates the final grades for each student. The final result should be rounded to two decimal places.

🧪 Test Cases:
Test Case 01:

Input:

Midterm Scores: [50, 70, 90]

Final Exam Scores: [60, 80, 100]

Output:
[55.0, 75.0, 95.0]

Test Case 02:

Input:

Midterm Scores: [95, 88]

Final Exam Scores: [70, 77]

Output:
[80.0, 80.4]

### CODE
````JAVA
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        double a[] = new double[n];
        
        for(int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }
        double b[] = new double[n];
        
        for(int i = 0; i < n; i++) {
            b[i] = s.nextInt();
        }
        
        double final_mark[] = new double[n];
        
        
        for(int i = 0; i < n; i++) {
            final_mark[i] = (a[i]*0.4) +(b[i]*0.6);
        }
        
                for(int i=0;i<n;i++)
                System.out.printf("%.2f ",final_mark[i]);
    }
}
````
6) Day 50 - Problem Solving for the day - 19.04.2025

Rotate array k times to the left

Input: [1, 2, 3, 4], k = 2

Output: [3, 4, 1, 2]

````java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[]=new int[n];
        for(int i=0;i<n;i++){
            a[i]=s.nextInt();
        }
        
        int k=s.nextInt();
        k=k%n;
        int rotate[]=new int[n];
        
        for(int i=0;i<n-k;i++){
            rotate[i]=a[i+k];
        }
        
        for(int i=0;i<k;i++){
            rotate[n-k+i]=a[i];
        }
                System.out.printf(Arrays.toString(rotate));
    }
}

````
7) Problem Solving for the day - 11.04.2025
A warehouse has multiple shelves represented by an array of weights.You must
determine if you can split the array into two parts with equal sum.
You're given an array of integers, where each element represents the weight on a
shelf.You need to determine if it's possible to split the array into two parts such that
the sum of the weights in both parts is equal.
Sample Input 01 :
int[] shelves = {1, 2, 3, 4, 6}
Sample Input 02 :
int[] shelves = {1, 2, 3}

````java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        boolean canSplit = false;

        for (int i = 0; i < n - 1; i++) {
            int sum1 = 0;
            int sum2 = 0;
            for (int j = 0; j <= i; j++) {
                sum1 += a[j];
            }
            for (int j = i + 1; j < n; j++) {
                sum2 += a[j];
            }
            if (sum1 == sum2) {
                canSplit = true;
                break;
            }
        }

        System.out.println(canSplit);
    }
}
````

