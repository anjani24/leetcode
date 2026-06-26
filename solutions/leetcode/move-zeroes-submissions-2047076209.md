# move zeroes/submissions/2047076209

**Platform:** LeetCode  
**Date:** 2026-06-26  

## Solution

```
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n= nums.size();

        int p=1;
        int i=0;

        while(i<n && p<n){
            
            if(nums[p]!=0 && nums[i]==0){
                swap(nums[i], nums[p]);
                i++;
                p++;
            }
            else if(nums[i]!=0){
                i++;
            }
            else if(nums[p]==0){
                p++;
            }

        }
    }
};
```
