## :zap: Question:

> Write a program to find the n-th ugly number.
> Ugly numbers are positive numbers whose prime factors only include 2, 3, 5. 
> Example:
> Input: n = 10
> Output: 12
> Explanation: 1, 2, 3, 4, 5, 6, 8, 9, 10, 12 is the sequence of the first 10 ugly numbers.
> Note:  
> 1. 1 is typically treated as an ugly number.
> 2. n does not exceed 1690.

## 	:peach: My Solution: 

```
class Solution {
    public int nthUglyNumber(int n) {
        if (n <= 0){
            return 0;
        } 
        List<Integer> uglyNums = new ArrayList<Integer>();
        uglyNums.add(1);

        int i2 = 0;
        int i3= 0;
        int i5= 0;

        while (uglyNums.size() < n) {
            int y2 = uglyNums.get(i2) * 2;
            int y3 = uglyNums.get(i3) * 3;
            int y5 = uglyNums.get(i5) * 5;

            int min = Math.min(y2, Math.min(y3, y5));
            uglyNums.add(min);

            if (min == y2) 
             i2++;
            if (min == y3) 
              i3++;
            if (min == y5) 
             i5++;
        }

        return uglyNums.get(uglyNums.size() - 1);
    }
}
```
