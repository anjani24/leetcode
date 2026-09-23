# minimum operations to reduce x to zero/submissions/2150605276

**Platform:** LeetCode  
**Date:** 2026-09-23  

## Solution

```
class Solution {
public:
    int minOperations(vector<int>& nums, int x) {

        int n = nums.size();

        // Prefix sum
        vector<int> pre(n + 1, 0);

        for(int i = 1; i <= n; i++) {
            pre[i] = pre[i - 1] + nums[i - 1];
        }

        // We need to keep a subarray with this sum
        int target = pre[n] - x;

        // If target is negative, impossible
        if(target < 0) {
            return -1;
        }

        unordered_map<int, int> mp;

        // prefix sum 0 occurs at index 0
        mp[0] = 0;

        int maxLen = -1;

        for(int i = 1; i <= n; i++) {

            int need = pre[i] - target;

            // Have we seen the required prefix sum?
            if(mp.find(need) != mp.end()) {

                int len = i - mp[need];

                maxLen = max(maxLen, len);
            }

            // Store only the first occurrence
            if(mp.find(pre[i]) == mp.end()) {
                mp[pre[i]] = i;
            }
        }

        // No subarray with sum = total - x
        if(maxLen == -1) {
            return -1;
        }

        // Remove everything outside the longest subarray
        return n - maxLen;
    }
};
```
