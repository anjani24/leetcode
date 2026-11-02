# maximum subarray/submissions/2187445354

**Platform:** LeetCode  
**Date:** 2026-11-02  

## Solution

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {

        // int maxs=nums[0];
        // int curr_sum=nums[0];
        // int i=1;

        // while(i<nums.size()){

        //     curr_sum = max(curr_sum + nums[i], nums[i]);
        //     maxs= max(maxs, curr_sum);
        //     i++;
        // }
        

        // return maxs; 

        //t2

        int sum=nums[0];
        int maxs=nums[0];

        for(int i=1; i<nums.size();i++){

            sum= max(sum+nums[i], nums[i]);
            maxs= max(sum, maxs);
        }
        return maxs;
    }
};
```
