# number of 1 bits/submissions/2039699997

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int hammingWeight(int n) {
        int count=0;

        for(int i =0; i<n; i++){
            count++;
            n &= (n-1);
        }
        return count;
        
    }
};
```
