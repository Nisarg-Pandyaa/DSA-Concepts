# Method 1
- TLE (for n>=10000 )</br> </br>
``` java
import java.util.*;

public class Solution {
    public static long solve(int n, int[] a) {
        
        if(n==1) return (long)a[0];


        int[] arr = new int[n-1];

        for(int i=1;i<n;i++){
            arr[i-1] = a[i];
        }
        long sum = a[0] + solve(n-1,arr);

        return sum;

    }
}
```

# Method 2
- Stack overflow (for n>=10000) </br> </br>
``` java
import java.util.*;

public class Solution {
    public static long solve(int n, int[] a) {
        
        if(n<=0) return (long)0;

        
        long sum = a[n-1] + solve(n-1,a);

        return sum;

    }
}
```
