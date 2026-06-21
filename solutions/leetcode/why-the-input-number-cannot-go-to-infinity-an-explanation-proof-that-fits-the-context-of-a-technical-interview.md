# Why the input number cannot go to infinity (an explanation/proof that fits the context of a technical interview)

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
public:
    bool isHappy(int n) {

        while(n/10!=0){
            int p=n;
            int sum =0;         
            while(p/10 !=0){
                int r=p%10;
                sum += (r*r);
                p=p/10;
            }
            sum += (p*p);
            n=sum;
        }

        if(n==1){
            return true;
        }
        return false;
        
    }
};
```
