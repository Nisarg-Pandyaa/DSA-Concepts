# Recursion 

- Fn calls itself (Directly or Indirectly) </br> </br>
- Used When `Big/Complex` Problem ka `Solution` ussi ki same type ki `Choti Problem` pr depend karta hea then we use Recursion. </br>
  - `Eg:` </br>
    2^n = ?
    - 2^4 = 2 x 2^3
    - 2^3 = 2 x 2^2
    - 2^2 = 2 x 2^1
    - 2^1 = 2 x 2^0
    - 2^0 = 1 -> `BASE CASE` </br> </br>
    - 2^n = 2 x 2^(n-1)
    - `F(n) = 2 x F(n-1)`        # Recursive Relation
   
    n! = ?
    - 5! = 5 x 4!
    - 4! = 4 x 3!
    - 3! = 3 x 2!
    - 2! = 2 x 1!
    - 1! = 1 x 0!
    - 0! = 1 -> `BASE CASE` </br> </br>
    - n! = n x (n-1)!
    - `F(n) = n x F(n-1)`        # Recursive Relation
</br> </br>

- RECURSION : (Mandatory) </br>
  1.) `BASE CASE` - Always Comes with `return` statement -> Iska matlab `RUK JAO`. If nai lagaya then `Segmentation Fault` kyuki `Stack Overflow` Ho Jayega </br> 
  2.) `RECURSIVE RELATION` -

  - One More Component : `PROCESSING` -> Kuch `print`, `increment`, `decrement` etc karna ho. </br>
 </br>
- Two Types Of Recursion : </br> </br>
  1.) Tail Recursion </br> 
  
  ```
  Fn(){
     BASE CASE;
     PROCESSING;
     RECURSIVE RELATION;
  }
  ```
  
  2.) Head Recursion
  ```
  Fn(){
     BASE CASE;
     RECURSIVE RELATION;
     PROCESSING;
  }
  ```

</br>
- Codes


```
package RECURSION;
import java.util.*;

public class lec1 {
    private static int factorial(int n1){

        //BASE CASE
        if(n1==0 || n1==1) return 1;

        /*
        int smallProblem = factorial(n1-1);
        int bigProblem = n1 * smallProblem;
        return bigProblem;
        */

        return n1 * factorial(n1-1);
    }

    private static int twoPowerN(int n2) {
        if(n2==0) return 1;

        /*
        int smallProblem = twoPowerN(n2 - 1);
        int bigProblem = 2 * smallProblem;
        return bigProblem;
        */

        return 2 * twoPowerN(n2-1);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n1 = sc.nextInt();
        System.out.println(factorial(n1));

        int n2 = sc.nextInt();
        System.out.println(twoPowerN(n2));
    }


}
```
    
    
