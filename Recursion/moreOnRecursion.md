- Ek case solve karne ka socho, baaki sare cases automatic recursion solve kar dega.

```
package RECURSION;
import java.util.*;

public class lec2 {
    public  static void move(int destination,int start){
        System.out.println("Current Position : "+start+", Destination : "+destination);
        if(start == destination){
            System.out.println("Reached!!");
            return;
        }

        start++;

        move(destination,start);
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int destination = 10;
        int start = 3;

        move(destination,start);

    }
}
```
