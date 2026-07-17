# bitwise and of numbers range/submissions/2071382026

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
    int rangeBitwiseAnd(int left, int right) {

        int count=0;

        while(left !=right){
            left>>=1;
            right>>=1;
            count++;
        }

        return left<<count;
    }
};
```
