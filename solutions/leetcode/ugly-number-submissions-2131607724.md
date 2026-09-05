# ugly number/submissions/2131607724

**Platform:** LeetCode  
**Date:** 2026-09-05  

## Solution

```
class Solution {
public:
    bool isUgly(int n) {
        if(n<1)return false;
        if(n==1)return true;

        while(n){
            if(n%2==0) n=n/2;
            else if(n%3==0) n=n/3;
            else if(n%5==0) n=n/5;
            else{
                break;
            }
        }
        return n>1?false:true;
    }
};
```
