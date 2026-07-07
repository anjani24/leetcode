# concatenate non zero digits and multiply by sum i/submissions/2059321406

**Platform:** LeetCode  
**Date:** 2026-07-07  

## Solution

```
class Solution {
public:
    long long sumAndMultiply(int n) {
        long long sum=0;
        int r=1;
        long long ans=0;
        int p=0;

        while(n!=0){
            p= n%10;

            if(p!=0){
                sum= sum + p;
                ans= ans + p*r;
                r= r*10;
            }
            n=n/10;

        }

        ans= ans*sum;
        return ans; 
    }
};
```
