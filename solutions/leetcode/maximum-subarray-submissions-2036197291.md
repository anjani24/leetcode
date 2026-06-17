# maximum subarray/submissions/2036197291

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {

        int maxs=nums[0];
        int curr_sum=nums[0];
        int i=1;

        while(i<nums.size()){

            curr_sum = max(curr_sum + nums[i], nums[i]);
            maxs= max(maxs, curr_sum);
            i++;
        }
        

        return maxs; 
    }
};
```
