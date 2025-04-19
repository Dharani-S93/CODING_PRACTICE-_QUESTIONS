

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
