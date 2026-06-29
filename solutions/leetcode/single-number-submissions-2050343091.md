# single number/submissions/2050343091

**Platform:** LeetCode  
**Date:** 2026-06-29  

## Solution

```
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int ans=0;

        for(auto & num: nums){
            ans ^= num;
        }

        return ans;
        
    }
};
```
