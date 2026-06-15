# generate parentheses/submissions/2033863785

**Platform:** LeetCode  
**Date:** 2026-06-15  

## Solution

```
class Solution {
public:
    vector<string> ans;
    void backtrack(int n, string & curr, int opencount, int closecount){
        if(opencount==n && closecount==n){
            ans.push_back(curr);
            return;
        }

        if(opencount<n){
            curr.push_back('(');
            backtrack(n, curr, opencount+1, closecount);
            curr.pop_back();
        }


        if(closecount< opencount){
            curr.push_back(')');
            backtrack(n, curr, opencount, closecount+1);
            curr.pop_back();
        }
    }

    vector<string> generateParenthesis(int n) {
        string curr;
        backtrack(n, curr, 0, 0);
        return ans;
        
    }
};
```
