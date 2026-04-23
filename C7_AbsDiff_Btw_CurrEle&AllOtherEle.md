- The `summation` of `absolute differences` between `nums[i]` and `all the other elements` in the array. </br> </br>
  - `e.g` : </br> For `nums[i]` => (nums[i] - nums[0]) + (nums[i] - nums[1]) + ... + (nums[i] - nums[i-1]) + (nums[i+1] - nums[i]) + (nums[i+2] - nums[i]) + ... + (nums[n-1] - nums[i]). </br> </br>
  - It can be simplified to : </br> 
    - = (nums[i] * i - `(nums[0] + nums[1] + ... + nums[i-1])`) + (`(nums[i+1] + nums[i+2] + ... + nums[n-1])` - nums[i] * (n-i-1))
    - = (nums[i] * i - `preSum[i-1]`) + ((`preSum[n-1]-preSum[i]`) - nums[i]*(n-i-1))

</br> </br>
- What It Looks Like : 
<img width="556" height="155" alt="image" src="https://github.com/user-attachments/assets/ec29926d-d458-4def-afa7-9b9e49afc28f" />
