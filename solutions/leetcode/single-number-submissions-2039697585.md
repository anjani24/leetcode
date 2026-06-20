# single number/submissions/2039697585

**Platform:** LeetCode  
**Date:** 2026-06-20  

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
