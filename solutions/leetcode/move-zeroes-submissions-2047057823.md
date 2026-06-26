# move zeroes/submissions/2047057823

**Platform:** LeetCode  
**Date:** 2026-06-26  

## Solution

```
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int c=0;

        for(int i=0; i< nums.size(); i++){
            if(nums[i]==0){
                nums.erase(nums.begin()+i);
                c++;
            }
        }
        for(int i=0; i<c;i++){
            nums.push_back(0);
        }
    }
};
```
