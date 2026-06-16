# jump game ii/submissions/2035512485

**Platform:** LeetCode  
**Date:** 2026-06-16  

## Solution

```
class Solution {
public:
    int jump(vector<int>& nums) {
        int left=0;
        int right=0;
        int jumps=0;
        int farthest=0;

        for(int i=0; i< nums.size()-1; i++){
            farthest= max (farthest, i+ nums[i]);
            if(i==right){
                jumps++;
                right = farthest;
            }
        }

        return jumps;
        
    }
};
```
