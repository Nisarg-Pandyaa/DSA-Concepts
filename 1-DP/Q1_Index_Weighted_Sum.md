# Index Weighted Sum

` F(k) = 0 * arrk[0] + 1 * arrk[1] + ... + (n - 1) * arrk[n - 1] `
</br>
<h3> Make It A DP Problem </h3> 
e.g : </br>
- num = [a,b,c,d,e] </br> </br>
- f(0) = 0*a + 1*b + 2*c + 3*d + 4*e </br> 
- f(1) = 0*e + 1*a + 2*b + 3*c + 4*d </br> </br>

- `f(1) - f(0) =  a + b + c + d - 4e` => `f(1) - f(0) =  (a + b + c + d +e) - 5e` </br> </br>

SO FOR ALL F[i] = 

<h3>f(k) = f(k-1) + sumOfArr - lenOfArray*num[n-k] </h3>  
NOTE : Not A Increasing/Decreasing 1D-DP </br> </br>
LC : 396 

