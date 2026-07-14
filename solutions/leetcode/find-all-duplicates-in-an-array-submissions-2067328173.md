# find all duplicates in an array/submissions/2067328173

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    vector<int> findDuplicates(vector<int>& nums) {
        vector<int> ans;

        for(int i=0; i< nums.size(); i++){
            
            int index= abs(nums[i])-1;

            if(nums[index]<0){
                ans.push_back(abs(nums[i]));
            }

            nums[index] = -nums[index];

        }
        return ans;
        
    }
};
```
