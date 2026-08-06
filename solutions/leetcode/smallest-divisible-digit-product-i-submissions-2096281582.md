# smallest divisible digit product i/submissions/2096281582

**Platform:** LeetCode  
**Date:** 2026-08-06  

## Solution

```
class Solution {
public:
    int smallestNumber(int n, int t) {

        n--;

        while(n++){
            int p=n;
            int prod=1;
            while(p!=0){
                prod= prod*p%10;
                p=p/10;
            }
            if(prod%t==0){
                return n;
            }
        }
        return n; 
    }
};
```
