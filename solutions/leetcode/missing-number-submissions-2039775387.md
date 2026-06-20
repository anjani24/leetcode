# missing number/submissions/2039775387

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int missingNumber(vector<int>& nums) {

        int ans;
        int n= nums.size();
        int a=0, b=0;

        for(int i=1; i<=n; i++){
            b= b+ i;
        }

        for(int i=0; i< n; i++){

            a= a+ nums[i];
        }

        return b-a;

        
    }
};
```
