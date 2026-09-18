# 😇 Actually Good Hints

**Platform:** LeetCode  
**Date:** 2026-09-18  

## Solution

```
class Solution {
public:
    bool canPartition(vector<int>& nums) {

        int n=nums.size();
        sort(nums.begin(), nums.end());
        int sum=0;

        for(int i=0; i<n;i++){
            sum+=nums[i];
        }

        if (sum%2==1)return false;

        sum= sum/2;

        vector<bool> dp(sum+1,false);
        dp[0]=true;

        for(int i=1; i<=sum; i++){

            for(int num:nums){
                if(num<=i){
                    dp[i]=dp[i-num] || dp[i];
                }
            }
        }
        return dp[n];
        
    }
};
```
