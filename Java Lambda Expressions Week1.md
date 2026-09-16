import java.io.*;
import java.util.*;
import java.security.*;

interface PerformOperation {
    boolean check(int a);
}

class MyMath {

    public boolean checker(PerformOperation p, int num) {
        return p.check(num);
    }

    // Returns true if odd
    PerformOperation isOdd() {
        return (int a) -> a % 2 != 0;
    }

    // Returns true if prime
    PerformOperation isPrime() {
        return (int a) -> {
            if (a < 2)
                return false;
            for (int i = 2; i * i <= a; i++) {
                if (a % i == 0)
                    return false;
            }
            return true;
        };
    }

    // Returns true if palindrome
    PerformOperation isPalindrome() {
        return (int a) -> {
            int original = a;
            int reverse = 0;

            while (a > 0) {
                reverse = reverse * 10 + a % 10;
                a /= 10;
            }

            return original == reverse;
        };
    }
}

public class Solution {

    public static void main(String[] args) throws IOException {
        MyMath ob = new MyMath();
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        int T = Integer.parseInt(br.readLine());

        while (T-- > 0) {
            StringTokenizer st = new StringTokenizer(br.readLine());
            int ch = Integer.parseInt(st.nextToken());
            int num = Integer.parseInt(st.nextToken());

            PerformOperation op;

            if (ch == 1) {
                op = ob.isOdd();
                System.out.println(ob.checker(op, num) ? "ODD" : "EVEN");
            } else if (ch == 2) {
                op = ob.isPrime();
                System.out.println(ob.checker(op, num) ? "PRIME" : "COMPOSITE");
            } else if (ch == 3) {
                op = ob.isPalindrome();
                System.out.println(ob.checker(op, num) ? "PALINDROME" : "NOT PALINDROME");
            }
        }
    }
}








OUTPUT:
<img width="540" height="328" alt="image" src="https://github.com/user-attachments/assets/40649725-f78c-41c9-95e8-5d3a93dd81f3" />










