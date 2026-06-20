# missing number

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int missingNumber(vector<int>& nums) {

        int n= nums.size();
        // int a=0;
        // int b= n*(n+1)/2;

        // for(int i=0; i< n; i++){

        //     a= a+ nums[i];
        // }
        // return b-a;  

//method 2 using XOR
        int ans= n;
        for(int i=0; i<n; i++){
            ans ^= i;
            ans ^= nums[i];

        }
        return ans;
    }
};
```
