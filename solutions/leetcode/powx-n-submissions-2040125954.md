# powx n/submissions/2040125954

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:

    double ans=0;
    double power(double x, int n){
        if(n==0){
            ans=1;
            return ans;
        }
        
        double half= power(x, n/2);
        if(n%2==0){
            ans= half* half;
        }
        else{
            ans= x* half* half;
        }
        return ans;

    }
    double myPow(double x, int n) {
        long long N=n;

        power(x, abs(N));
    
        if(n>=0){
            return ans;
        }
        return 1/ans;
    }
};
```
