# removing minimum and maximum from array/submissions/2125020022

**Platform:** LeetCode  
**Date:** 2026-08-30  

## Solution

```
class Solution {
public:
    int minimumDeletions(vector<int>& nums) {
        int n= nums.size();
        if(n==1) return 1;

        int ans=0;
        int a=INT_MIN;
        int b=INT_MAX;
        int idx1=0;
        int idx2=0;
        
        for(int i=0; i<n ;i++){
            if(nums[i]>a){
                a=nums[i];
                idx1=i;
            }
            if(nums[i]<b){
                b=nums[i];
                idx2=i;
            }
        }

        int l = min(idx1, idx2);
        int r = max(idx1, idx2);

        int front = r + 1;
        int back = n - l;
        int both = (l + 1) + (n - r);

        return min({front, back, both});

        
    }
};
```
