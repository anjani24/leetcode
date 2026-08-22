# check divisibility by digit sum and product/submissions/2115675773

**Platform:** LeetCode  
**Date:** 2026-08-22  

## Solution

```
class Solution {
public:
    bool checkDivisibility(int n) {

        int r=n;
        int sum=0;
        int prod=1;
        

        while(n>0){
            int p=n%10;

            sum+= p;
            prod*=p;

            n=n/10;
        }

        if(r%(sum+prod)==0){
            return true;
        }
        return false;


        
    }
};
```
