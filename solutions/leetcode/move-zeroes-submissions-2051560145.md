# move zeroes/submissions/2051560145

**Platform:** LeetCode  
**Date:** 2026-06-30  

## Solution

```
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        
        int p=0;
        int i=0;
        
        while(i< nums.size()){
            
            if(nums[i]!=0){
                swap(nums[i], nums[p]);
                p++;
                i++;
            }
            else{
                i++;
            }
            
        }
    }
       
};

```
