# Hint

**Platform:** LeetCode  
**Date:** 2026-08-05  

## Solution

```
class Solution {
public:
    int singleNonDuplicate(vector<int>& nums) {
        int p=nums[0];
        for(int i=1; i<nums.size(); i++){

            p= p^nums[i];
        }
        return p;
        
    }
};
```
