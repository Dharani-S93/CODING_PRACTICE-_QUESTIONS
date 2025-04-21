


---

### ✈️ Airline's Maintenance System

> Seats with even-numbered seat IDs need special cleaning. Replace all even numbers with `0`.

**Test Cases:**
- Input: `[2, 4, 6, 8]` → Output: `[0, 0, 0, 0]`
- Input: `[12, 13, 14]` → Output: `[0, 13, 0]`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int[] a = new int[n];

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
```

---

### 🏅 Top Two Unique Scores

> Return the two highest unique scores from a list.

**Test Cases:**
- `[88, 95, 70, 95, 60]` → `[95, 88]`
- `[85, 85, 85]` → `[85]`
- `[76]` → `[76]`
- `[91, 91, 89, 89, 88]` → `[91, 89]`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        Arrays.sort(a);
        int[] temp = new int[n];
        int j = 0;

        for (int i = 0; i < n; i++) {
            if (i == 0 || a[i] != a[i - 1]) {
                temp[j++] = a[i];
            }
        }

        if (j >= 2) {
            System.out.println("[" + temp[j - 1] + ", " + temp[j - 2] + "]");
        } else if (j == 1) {
            System.out.println("[" + temp[0] + "]");
        } else {
            System.out.println("[]");
        }
    }
}
```

---

### 🧹 Room Rating Tracker

> Convert negative room ratings to their square (to represent issue severity). Leave positives unchanged.

**Test Cases:**
- `[1, -4, 2, -8, 5]` → `[1, 16, 2, 64, 5]`
- `[0, 5, 10]` → `[0, 5, 10]`
- `[-9, -5, -7]` → `[81, 25, 49]`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        for (int i = 0; i < n; i++) {
            if (a[i] < 0) {
                a[i] = a[i] * a[i];
            }
        }

        System.out.println(Arrays.toString(a));
    }
}
```

---

### 🛒 Supermarket App: Cart Total Calculator

> Apply discounts based on individual item price and total cart cost.

**Discount Rules:**
1. 10% off items > 50
2. Additional 5% off cart if total > 200

**Test Cases:**
- `[100, 50, 75, 30]` → `276.25`
- `[10, 20, 30, 50]` → `110.0`
- `[150, 100, 200]` → `400.0`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        double[] a = new double[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextDouble();
        }

        double total = 0;

        for (int i = 0; i < n; i++) {
            if (a[i] > 50) {
                a[i] *= 0.9;
            }
            total += a[i];
        }

        if (total > 200) {
            total *= 0.95;
        }

        System.out.printf("%.2f", total);
    }
}
```

---

### 🎓 Final Grade Calculator

> Combine midterm and final exam scores: 40% midterm + 60% final.

**Test Cases:**
- `[50, 70, 90]`, `[60, 80, 100]` → `[55.0, 75.0, 95.0]`
- `[95, 88]`, `[70, 77]` → `[80.0, 80.4]`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        double[] mid = new double[n];
        double[] fin = new double[n];
        double[] finalGrades = new double[n];

        for (int i = 0; i < n; i++) {
            mid[i] = s.nextDouble();
        }

        for (int i = 0; i < n; i++) {
            fin[i] = s.nextDouble();
        }

        for (int i = 0; i < n; i++) {
            finalGrades[i] = mid[i] * 0.4 + fin[i] * 0.6;
        }

        for (int i = 0; i < n; i++) {
            System.out.printf("%.2f ", finalGrades[i]);
        }
    }
}
```

---

### 🔄 Rotate Array Left

> Rotate an array `k` times to the left.

**Test Case:**  
- Input: `[1, 2, 3, 4]`, `k = 2` → Output: `[3, 4, 1, 2]`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int k = s.nextInt();
        k = k % n;

        int[] rotated = new int[n];

        for (int i = 0; i < n - k; i++) {
            rotated[i] = a[i + k];
        }

        for (int i = 0; i < k; i++) {
            rotated[n - k + i] = a[i];
        }

        System.out.println(Arrays.toString(rotated));
    }
}
```

---

### 📦 Equal Shelf Split Checker

> Can you split the shelf weights into two parts with equal sums?

**Test Cases:**
- `[1, 2, 3, 4, 6]` → `true`
- `[1, 2, 3]` → `false`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        boolean canSplit = false;

        for (int i = 0; i < n - 1; i++) {
            int sum1 = 0;
            int sum2 = 0;

            for (int j = 0; j <= i; j++) sum1 += a[j];
            for (int j = i + 1; j < n; j++) sum2 += a[j];

            if (sum1 == sum2) {
                canSplit = true;
                break;
            }
        }

        System.out.println(canSplit);
    }
}
```

---

### 🛍️ Cart Price Tracker

> Track total cost, remove duplicates, and sort unique prices in descending order.

**Test Cases:**
- `[150, 150, 150, 150]` → Total: 600, Unique: `[150]`
- `[999, 499, 799, 199, 499, 999, 199]` → Total: 4194, Unique: `[999, 799, 499, 199]`

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);

        int n = s.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int total = 0;
        for (int value : a) {
            total += value;
        }

        System.out.println("The Total is: " + total);

        Arrays.sort(a);
        ArrayList<Integer> unique = new ArrayList<>();

        for (int i = 0; i < n; i++) {
            if (i == 0 || a[i] != a[i - 1]) {
                unique.add(a[i]);
            }
        }

        Collections.sort(unique, Collections.reverseOrder());
        System.out.println("Unique prices in Descending Order: " + unique);
    }
}
```

---

