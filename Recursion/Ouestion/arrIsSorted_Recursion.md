# Method 1

``` java
public class Solution {
    public static int isSorted(int n, int []a) {
        
        if(n==0 || n==1) return 1;

        if(a[0]>a[1]) return 0;
        else{
            int[] arr = new int[n-1];
            for(int i=1;i<n;i++){
                arr[i-1] = a[i];
            }
            int ans = isSorted(n-1,arr);
            return ans;
        }
    }
}
