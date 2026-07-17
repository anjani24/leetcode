# valid palindrome ii/submissions/2071253438

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
    bool isP(string s, int i, int j){
        while( i<j ){
            if(s[i]!=s[j]){
                return false;
            }
            i++;
            j--;
        }
        return true;
    }

    bool validPalindrome(string s) {

        int i=0;
        int j= s.size()-1;

        while(i<j){

            if(s[i]!= s[j]){

                return isP(s, i+1, j) || isP(s, i, j-1);
            }
            i++;
            j--;
        }
        return true;  
    }
};
```
