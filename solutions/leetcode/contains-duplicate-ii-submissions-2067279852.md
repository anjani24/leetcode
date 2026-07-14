# contains duplicate ii/submissions/2067279852

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {

        int i=0;
        int j=1;

        while(i<nums.size()-1 && j< nums.size()){

            if(nums[i]==nums[j] && abs(i-j)<=k){
                return true;
            }
            if(abs(i-j)>k){
                i++;
                j= i+1;
            }
            else{
                j++;
            }
        }

        return false;
        
    }
};
```
