# smallest index with digit sum equal to index/submissions/2151825044

**Platform:** LeetCode  
**Date:** 2026-09-24  

## Solution

```
class Solution {
public:
    int smallestIndex(vector<int>& nums) {

        for(int i=0; i<nums.size();i++){

            int num= nums[i];
            int sum=0;
            
            while(num){
                int p=num%10;
                sum =sum+p;
                num=num/10;
            }

            if(i==sum){
                return i;
            }
        }
        return -1;
        
    }
};
```
