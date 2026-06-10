```java
        int max1 = Integer.MIN_VALUE;
        int max2 = Integer.MIN_VALUE;

        for(int n : nums){
            if(n>max1){
                max2= max1;
                max1 = n;
            }
            else if(n>max2){
                max2 = n;
            }

            if(n<min2){
                min1 = min2;
                min2 = n;
            }
            else if(n<min1) min1 = n;
            
        }
```
