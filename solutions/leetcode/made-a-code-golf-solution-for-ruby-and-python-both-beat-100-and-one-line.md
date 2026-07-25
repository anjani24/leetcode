# Made a code golf solution for Ruby and Python, both beat 100% and one-line

**Platform:** LeetCode  
**Date:** 2026-07-25  

## Solution

```
class Solution {
public:
    int maxProduct(int n) {

        int prod=1;
        if(n==0){
            return 0;
        }

        while(n!=0){
            int k= n%10;
            if(k!=0){
                prod= prod * k;
            }
            n=n/10;

        }
        return prod;
        
    }
};
```
