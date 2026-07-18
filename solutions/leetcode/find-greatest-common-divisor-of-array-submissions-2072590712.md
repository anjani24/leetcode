# find greatest common divisor of array/submissions/2072590712

**Platform:** LeetCode  
**Date:** 2026-07-18  

## Solution

```
class Solution {
public:
    int findGCD(vector<int>& nums) {


        auto max_n= max_element(nums.begin(), nums.end());
        int maxn= *max_n;
        auto min_n= min_element(nums.begin(), nums.end());
        int minn= *min_n;
        return gcd(maxn, minn);
        
    }
};
```
