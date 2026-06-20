# reverse bits/submissions/2039744165

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int reverseBits(int n) {

        int ans=0;

        for(int i=0; i<32; i++){
            ans= ans<<1| (n&1);
            n=n>>1;
        }
        return ans;
    }
};
```
