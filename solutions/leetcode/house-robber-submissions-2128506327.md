# house robber/submissions/2128506327

**Platform:** LeetCode  
**Date:** 2026-09-02  

## Solution

```
class Solution {
public:
    
    int rob(vector<int>& nums) {
        int s= nums.size();
        vector<int> cost(s);
        cost[0]=nums[0];

        if(s==1){
            return nums[0];
        }
        cost[1]=max(nums[0],nums[1]);

        for(int i=2; i<s;i++){
            cost[i]= max(cost[i-2]+nums[i], cost[i-1]);
        }
        return cost[s-1];
        
    }
};
```
