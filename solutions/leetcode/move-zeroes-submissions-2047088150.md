# move zeroes/submissions/2047088150

**Platform:** LeetCode  
**Date:** 2026-06-26  

## Solution

```
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n= nums.size();

        int p=0;
        int i=0;

        for(int i=0;  i<n; i++){

            if(nums[i]!=0){
                swap(nums[i], nums[p]);
                p++;
            }

        }
    }
};
```
