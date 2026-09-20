# The answer is either 0 or 1 why ?

**Platform:** LeetCode  
**Date:** 2026-09-20  

## Solution

```
class Solution {
public:
    int minOperations(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int n= nums.size();
        int med= nums[n/2];
        int ops=0;
        for(int i=0 ;i<n; i++){
            ops = ops+ abs( nums[i]-med);

        }
        return ops;


        
    }
};
```
