# sum of gcd of formed pairs/submissions/2069895200

**Platform:** LeetCode  
**Date:** 2026-07-16  

## Solution

```
class Solution {
public:
    long long gcdSum(vector<int>& nums) {

        int n=nums.size();
        int mx=0;
        vector<int> prefixGcd(n);

        for(int i=0; i<n ;i++){
            mx= max(nums[i],mx);
            prefixGcd[i]= gcd(nums[i],mx);
        }

        sort(prefixGcd.begin(),prefixGcd.end());

        int i=0;
        int j=n-1;
        long long sum=0;

        while(i<j){
            sum= sum+ gcd(prefixGcd[i], prefixGcd[j]);
            i++;
            j--;
        }
        return sum;
        
    }
};
```
