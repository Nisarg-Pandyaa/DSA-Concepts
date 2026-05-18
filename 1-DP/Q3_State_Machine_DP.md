# State Machine DP
- Also Known As State-Transition DP or Automaton DP
- It also shares a structural category with Prefix/Suffix DP problems.

----

``` java
import java.util.*;

public class Main{
    
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        
        int t = sc.nextInt();
        
        while(t-- > 0){
            
            StringBuilder sb = new StringBuilder(sc.next());
            
            int n = sb.length();
            if(n==0){
                System.out.println(0);
                continue;
            }
            
            long ans;
            
            long dp0 = 0; // min deletions to have a string = 22222.....
            long dp1 = 0; // min deletions to have a string = 22222....13133111....
            
            for(int i=0;i<n;i++){
                char ch = sb.charAt(i);
                
                if(ch=='4'){
                    dp0++; dp1++;     // no need of 4 in both strings
                }
                else if(ch=='2'){
                    long nextDP0 = dp0;           //  no deletion of 2 require for 22222....
                    long nextDP1 = dp1 + 1;       //  delete 2 bcz we already assume 222s..131313..
                    
                    dp0 = nextDP0;
                    dp1 = nextDP1;
                }
                else if(ch=='1' || ch=='3'){
                    long nextDP0 = dp0 + 1;      // delete either 1 or 3 for 2222...
                    long nextDP1 = Math.min(dp0,dp1);        // 222... -> 2222...1|3 OR 222...133..1|3 -> DP1 = MIN(222... , 222...133..)
                    
                    dp0 = nextDP0;
                    dp1 = nextDP1;
                }
            }
            
            ans = Math.min(dp0,dp1);
            
            System.out.println(ans);
        }
    } 
    

}
```
