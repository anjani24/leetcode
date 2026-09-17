# [python]
"Case2" IS WRONG!

**Platform:** LeetCode  
**Date:** 2026-09-17  

## Solution

```
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int k = 0; // Pointer for the next valid element position
        
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] != val) {
                nums[k] = nums[i];
                k++;
            }
        }
        
        return k; // k automatically represents the count of elements not equal to val
    }
};

```
