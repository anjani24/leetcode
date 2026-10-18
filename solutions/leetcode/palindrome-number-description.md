# palindrome number/description

**Platform:** LeetCode  
**Date:** 2026-10-18  

## Solution

```
class Solution {
public:
    bool isPalindrome(int x) {
 
        int y = x;
        long long rev=0;

        if(y<0){
            return false;
        }

        while(y!=0){
            int r= y%10;
            rev= rev*10+r;
            y=y/10;
        }
        return x==rev;
    }
};
```
