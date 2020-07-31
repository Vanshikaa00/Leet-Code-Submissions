# :zap: Question

!! A FEW TESTCASES PASSED IN THIS QUESTION !!

> Given a 2D board and a word, find if the word exists in the grid.
> The word can be constructed from letters of sequentially adjacent cell, where "adjacent" cells are those horizontally or vertically neighboring. The same letter cell may not be used more than once.
```
Example:

board =
[
  ['A','B','C','E'],
  ['S','F','C','S'],
  ['A','D','E','E']
]

Given word = "ABCCED", return true.
Given word = "SEE", return true.
Given word = "ABCB", return false.
 

Constraints:

board and word consists only of lowercase and uppercase English letters.
1 <= board.length <= 200
1 <= board[i].length <= 200
1 <= word.length <= 10^3
```
 # :peach: Solution
 ```
 class Solution {
  public boolean exist(char[][] board, String word) {
        char ch[]=word.toCharArray();
        int i,j,k,m=board.length,n=board[0].length;
        boolean res=true;
        for(k=0;k<ch.length;k++){
            for(i=0;i<m;i++){
                for(j=0;j<n;j++){
                    if(ch[k]!=board[i][j]){
                        res=false;
                    }
                    else{
                        res=true;
                        break;
                    }
                }
            }
        }
        return res;
    }
}
 ```
