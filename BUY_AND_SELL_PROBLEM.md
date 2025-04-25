### BUY AND SELL PROBLEM

````JAVA

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int[] a = new int[n];
        
        for(int i = 0; i < n; i++) {
            a[i] = s.nextInt();  
        }
        
        int c5 = 0, c10 = 0; 

        boolean give = true;
        
        for(int i = 0; i < n; i++) {
            if(a[i] == 5) {
                c5++; 
            }
            else if(a[i] == 10) {
                if(c5 >= 1) {
                    c5--;
                    c10++;
                } else {
                    give = false;
                    break;
                }
            }
            else if(a[i] == 15) {
                if(c10 >= 1) {
                    c10--;
                } else if(c5 >= 2) {
                    c5 -= 2;    
                } else {
                    give = false;
                    break;
                }
            }
        }

        if(give) {
            System.out.println("YES");
        } else {
            System.out.println("NO");
        }
    }
}

````JAVA


