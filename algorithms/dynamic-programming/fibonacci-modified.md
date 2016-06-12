Since js does not have big int. The solution to this problem is in java. 
[**Solution**](https://www.hackerrank.com/challenges/fibonacci-modified)
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int i1 = scanner.nextInt();
        int i2 = scanner.nextInt();
        int n = scanner.nextInt();
        System.out.println(calculate(i1, i2, n));
    }

    public static String calculate(int i1, int i2, int n) {
        BigInteger[] series = new BigInteger[n];
        series[0] = BigInteger.valueOf(i1);
        series[1] = BigInteger.valueOf(i2);
        int i = 2;
        while(i < n) {
           series[i] = series[i-1].multiply(series[i-1]).add(series[i-2]);
           i++;
        }
        return series[n-1].toString();
    }
}
```
