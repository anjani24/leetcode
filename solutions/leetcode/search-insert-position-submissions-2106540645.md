# search insert position/submissions/2106540645

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {

        int l=0;
        int r=nums.size()-1;
        int mid;

        if(target< nums[l]) return 0;
        if(target>nums[r]) return r+1;

        while(l<=r){
            mid= l+(r-l)/2;
            if(target==nums[mid]) return mid;
            if(target< nums[mid]){ r= mid-1;
            }
            else{
                l= mid+1;
            }
        }

        return (l+r);
        
    }
};
```
