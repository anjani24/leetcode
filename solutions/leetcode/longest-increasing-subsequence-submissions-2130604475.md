# longest increasing subsequence/submissions/2130604475

**Platform:** LeetCode  
**Date:** 2026-09-04  

## Solution

```
class Solution {
public:
    int solve(vector<int> &nums, vector<int> &dp, int p){
        if(p==0){
            return 1;
        }

        if(dp[p]!=-1){
            return dp[p];
        }
        else{
            dp[p]=1;
        }

        for(int i=0; i<p; i++){
            if(nums[i]<nums[p]){
                dp[p]= max(dp[p], solve(nums,dp, i)+1);
            }
        }
        return dp[p];

    }
    int lengthOfLIS(vector<int>& nums) {

        int n= nums.size();
        vector<int> dp(n+1,-1);
        int ans=0;

        for(int i=0; i<n; i++){
            ans= max(ans,solve(nums, dp,i));
        }
        return ans;
    }
};
```
