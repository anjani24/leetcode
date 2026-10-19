# find target indices after sorting array/submissions/2176538177

**Platform:** LeetCode  
**Date:** 2026-10-19  

## Solution

```
class Solution {
public:
    vector<int> targetIndices(vector<int>& nums, int target) {

        sort(nums.begin(),nums.end());
        int i=0;
        int n=nums.size();
        vector<int>ans;
        while(i<n){
            if(nums[i]==target) ans.push_back(i);
            i++;
        }
        return ans;
        
    }
};
```
