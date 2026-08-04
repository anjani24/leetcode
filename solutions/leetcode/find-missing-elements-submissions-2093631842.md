# find missing elements/submissions/2093631842

**Platform:** LeetCode  
**Date:** 2026-08-04  

## Solution

```
class Solution {
public:
    vector<int> findMissingElements(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int n=nums.size();
        int l=nums[0];
        int r=nums[n-1];
        vector<int> ans;
        for(int i=1; i< n; i++){
            int diff= nums[i]-nums[i-1];
            int a=nums[i-1];
            while(diff!=1){
                ans.push_back(a+1);
                a++;
                diff--;
            }
        }
        return ans;
    }
};
```
