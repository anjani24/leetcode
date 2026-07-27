# maximum product of two elements in an array/submissions/2082780916

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
class Solution {
public:
    int maxProduct(vector<int>& nums) {

        int i=INT_MIN;
        int j=INT_MIN;

        for(int p=0; p< nums.size(); p++){
            if(nums[p]>i){
                j= i;
                i= nums[p];
            }
            else if(nums[p]>j){
                j= nums[p];
            }
        }

        return (i-1)*(j-1); 
    }
};
```
