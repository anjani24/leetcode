# jump game/submissions/2055005818

**Platform:** LeetCode  
**Date:** 2026-07-03  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums){
        int reachable_idx=0;
        for(int i=0; i<nums.size();i++){
            reachable_idx=max(reachable_idx,i+nums[i]);
            if(reachable_idx>= nums.size()-1){
                return true;
            }
        }
        return false;   

    }
};

```
