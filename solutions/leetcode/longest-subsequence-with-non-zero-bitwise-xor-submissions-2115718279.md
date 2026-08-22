# longest subsequence with non zero bitwise xor/submissions/2115718279

**Platform:** LeetCode  
**Date:** 2026-08-22  

## Solution

```
class Solution {
public:
    int longestSubsequence(vector<int>& nums) {
        int total_xor = 0;
        bool has_non_zero = false;
        
        for (int num : nums) {
            total_xor ^= num;
            if (num != 0) {
                has_non_zero = true;
            }
        }
        
        // Case 1: The entire array yields a non-zero XOR sum
        if (total_xor != 0) {
            return nums.size();
        }
        
        // Case 2: Total XOR is 0, but we can drop 1 non-zero element
        if (has_non_zero) {
            return nums.size() - 1;
        }
        
        // Case 3: The array contains only zeros
        return 0;
    }
};

```
