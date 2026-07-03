# jump game/submissions/2055010231

**Platform:** LeetCode  
**Date:** 2026-07-03  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums){
        int farthest=0;
        for(int i=0;i<nums.size();i++)
        {

            farthest=max(farthest,nums[i]+i);
            if(farthest<=i)return false;
            if(farthest>=nums.size()-1)return true;
        }
        return false;
    }
};//submit fastt
```
