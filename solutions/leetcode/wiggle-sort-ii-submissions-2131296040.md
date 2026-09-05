# wiggle sort ii/submissions/2131296040

**Platform:** LeetCode  
**Date:** 2026-09-05  

## Solution

```
class Solution {
public:
    void wiggleSort(vector<int>& nums) {

        sort(nums.begin(), nums.end());
        int n=nums.size();

        vector<int> ans(n);
        int p= n-1;

        for(int i=1; i<n;i=i+2){
            ans[i]=nums[p];
            p--;
        }
        for(int i=0; i<n; i=i+2){
            ans[i]=nums[p];
            p--;
        }
        nums=ans;
        
    }
};
```
