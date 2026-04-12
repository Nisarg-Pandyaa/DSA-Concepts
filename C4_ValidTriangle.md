# Triangle Validity

- A triangle is valid if the sum of any two sides is strictly greater than the third side:
  - `a+b > c` && `b+c > a` && `c+a > b`
 
---
 
- If the triangle is valid, use the Law of Cosines to find each internal angle. For a triangle with sides a,b & c : </br> </br>
  - A = (b*b + c*c - a*a)/(2*b*c); => Convert to Radian (Use the inverse cosine function [acos or math.acos]) => Convert to Degrees (multiply by (180/Math.PI))
  - B = ( c*c + a*a - b*b )/(2*a*c); => "
  - C = (a*a+b*b - c*c)/(2*a*b); => " </br> </br>
 
```
double A = (b*b + c*c - a*a) / (2.0 * b * c);
double angA = Math.toDegrees(Math.acos(A));
```

---

- Inbuilt Functions Used :

  - `Math.toDegrees()` => Convert To Degrees
  - `Math.acos()` => Convert To Radian
  - `Math.PI` => 3.14


 
    



  

