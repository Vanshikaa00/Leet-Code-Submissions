## :zap: Question:

> The Hamming distance between two integers is the number of positions at which the corresponding bits are different.
> Given two integers x and y, calculate the Hamming distance.  
> Note:
> 0 ≤ x, y < 231.  
> Example:  
> Input: x = 1, y = 4  
> Output: 2  
> Explanation:  
> 1   (0 0 0 1)  
> 4   (0 1 0 0)  
> &nbsp; &nbsp; &nbsp; &nbsp; ↑  &nbsp;  ↑  
> The above arrows point to positions where the corresponding bits are different.

## 	:peach: My Solution: 

```
class Solution {
    public int hammingDistance(int x, int y) {
        String b1=Integer.toBinaryString(x);
        String b2=Integer.toBinaryString(y);
        int l1=b1.length();
        int l2=b2.length();
        if(l1>l2){
        b2=String.format("%1$" + l1 + "s", b2).replace(' ', '0');
        }
        if(l2>l1){
            b1=String.format("%1$" + l2 + "s", b1).replace(' ', '0');
        }
        int a1[]=new int[b1.length()];
        int a2[]=new int[b2.length()];
        int i,j,count=0,k=0,l=0;
        for(i=0;i<b1.length();i++){
            char c =b1.charAt(i); 
            a1[k++]=Integer.parseInt(String.valueOf(c));
        }
           for(i=0;i<b2.length();i++){
             char c =b2.charAt(i); 
            a2[l++]=Integer.parseInt(String.valueOf(c));
        }
        for(i=0;i<k;i++){
                if(a1[i]!=a2[i]){
                    count++;
                
            }
        }
        return count;
    }
}

```
