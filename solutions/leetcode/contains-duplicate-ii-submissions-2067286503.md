# contains duplicate ii/submissions/2067286503

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {

        int i=0;
        int j=k;

        while(j< nums.size() && abs(i-j)<=k){

            if(nums[i]==nums[j] && abs(i-j)<=k){
                return true;
            }
            if(j-i==1){
                j++;
            }
            i++;

        }

        return false;
        
    }
};
```
