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
        int maxp=0;
        int q=n;

        while(q!=0){
            int a= q%10;
            int k= q/10;
            while(k!=0){
                int b= k%10;
                prod= a*b;
                maxp= max(prod, maxp);
                k=k/10;
            }

            q=q/10;


        }
        return maxp;
        
    }
};
```
