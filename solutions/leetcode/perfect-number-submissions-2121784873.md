# perfect number/submissions/2121784873

**Platform:** LeetCode  
**Date:** 2026-08-27  

## Solution

```
class Solution {
public:
    bool checkPerfectNumber(int num) {

        int ans=num;
        int sum=0;

        for(int i=1; i<ans/2+1; i++){
            if(ans%i==0){
                sum+=i;
            }
        }
        return sum==num;
    }
};
```
