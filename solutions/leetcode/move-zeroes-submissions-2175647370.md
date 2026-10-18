# move zeroes/submissions/2175647370

**Platform:** LeetCode  
**Date:** 2026-10-18  

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

//0, 1, 0, 3, 12
//i ,j
//1, 3, 0, 0, 12
//      i,  , j

//1,5,0,0,6,44
//    i,  j
```
