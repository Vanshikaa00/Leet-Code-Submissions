## :zap: Question:

> You have a total of n coins that you want to form in a staircase shape, where every k-th row must have exactly k coins.
> Given n, find the total number of full staircase rows that can be formed.
> n is a non-negative integer and fits within the range of a 32-bit signed integer.
> Example 1:
> n = 5
> The coins can form the following rows:  
> ¤  
> ¤ ¤  
> ¤ ¤  
> Because the 3rd row is incomplete, we return 2.

## 	:peach: My Solution: 

```
import java.util.*;
class Solution {
    public int arrangeCoins(int n) {
        int i,left=n,count=0,req;
        boolean insert=false;
        for(i=0;i<n;i++){
            req=i+1;
            if(req<=left){
                insert=true;
                left=left-req;
                count++;
            }
            else{
                break;
            }
        }
        return count;
    }
    public static void main(String args[]){
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        Solution s1=new Solution();
        int result=s1.arrangeCoins(n);
        System.out.print(result);
    }
}
```
