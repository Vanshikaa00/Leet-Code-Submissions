# :zap: Question

> Given two binary strings, return their sum (also a binary string).
> The input strings are both non-empty and contains only characters 1 or 0.
> Example 1:
> Input: a = "11", b = "1"
> Output: "100"
> Example 2:
> Input: a = "1010", b = "1011"
> Output: "10101"
> Constraints:
> Each string consists only of '0' or '1' characters.
> 1 <= a.length, b.length <= 10^4
> Each string is either "0" or doesn't contain any leading zero.

# :peach: Solution
```
class Solution {
    public String addBinary(String a, String b) {
        int l = Math.max(a.length(), b.length());
        a = String.format("%1$" + l + "s", a).replace(' ', '0');
        b = String.format("%1$" + l + "s", b).replace(' ', '0');
        int x, y, i, sum, flag = 0;
        StringBuilder res = new StringBuilder();
        for (i = l - 1; i >= 0; i--) {
            x = Character.getNumericValue(a.charAt(i));
            y = Character.getNumericValue(b.charAt(i));
            sum = x + y + flag;
            if (sum >= 2) {
                res.append(sum - 2);
                flag = 1;
            } else {
                flag = 0;
                res.append(sum);
            }
        }
        if (flag == 1) {
            res.append("1");
        }
        return res.reverse().toString();
    }
}
```
