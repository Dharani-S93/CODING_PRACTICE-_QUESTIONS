## CODE
````java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);

        System.out.println("ENTER N VALUE: ");
        int n = s.nextInt();

        int[] start = new int[n];
        int[] end = new int[n];

        System.out.println("ENTER START VALUES: ");
        for (int i = 0; i < n; i++) {
            start[i] = s.nextInt();
        }

        System.out.println("ENTER END VALUES: ");
        for (int i = 0; i < n; i++) {
            end[i] = s.nextInt();
        }

        Integer[] meetings = new Integer[n];
        for (int i = 0; i < n; i++) {
            meetings[i] = i;
        }

        Arrays.sort(meetings, (a, b) -> end[a] - end[b]);

        int count = 1;
        int lastEnd = end[meetings[0]];

        System.out.println("Selected Meetings:");
        System.out.println(start[meetings[0]] + " " + end[meetings[0]]);

        for (int i = 1; i < n; i++) {
            if (start[meetings[i]] >= lastEnd) {
                System.out.println(start[meetings[i]] + " " + end[meetings[i]]);
                lastEnd = end[meetings[i]];
                count++;
            }
        }

        System.out.println("The number of meetings is: " + count);
    }
}

````

-----

### OUPUT
````JAVA
