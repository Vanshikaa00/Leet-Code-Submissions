## :zap: Question

Given an input string, reverse the string word by word.

 

Example 1:

Input: "the sky is blue"
Output: "blue is sky the"
Example 2:

Input: "  hello world!  "
Output: "world! hello"
Explanation: Your reversed string should not contain leading or trailing spaces.
Example 3:

Input: "a good   example"
Output: "example good a"
Explanation: You need to reduce multiple spaces between two words to a single space in the reversed string.
 

Note:

A word is defined as a sequence of non-space characters.
Input string may contain leading or trailing spaces. However, your reversed string should not contain leading or trailing spaces.
You need to reduce multiple spaces between two words to a single space in the reversed string.

## :peach: Solution
```
class Solution {
    public String reverseWords(String ss) {
        String s=ss.replaceAll("\\s+", " ");
        String str[]=s.split(" ");
        String ans="";
        for(int i=str.length-1;i>=0;i--){
        ans=ans+str[i]+" ";
        }
        ans=ans.trim();
        return ans;
    }
}
```
