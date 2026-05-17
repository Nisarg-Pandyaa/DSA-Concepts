``` java
bool recursiveBinarySearch(int[] arr, int l, int r, int k){

      // base case

      // element not found
      if(l>r) return false;

      int m = l + (r-l)/2;

      // element found
      if(arr[m]==k) return true;

      if(arr[m] < k) return recursiveBinarySearch(arr, m+1, r, k);
      else return recursiveBinarySearch(arr, l, m-1, k);

}
```
