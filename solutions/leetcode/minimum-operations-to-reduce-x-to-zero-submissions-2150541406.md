# minimum operations to reduce x to zero/submissions/2150541406

**Platform:** LeetCode  
**Date:** 2026-09-23  

## Solution

```
class Solution {
public:
    int minOperations(vector<int>& nums, int x) {

        sort(nums.begin(), nums.end());

        vector<int> dp(x+1,-1);
        dp[0]=0;

        for(int n: nums){
            for(int i=x; i>=0; i--){
                if(n<=i){
                    if(dp[i-n]!=-1){
                        if(dp[i]!=-1){
                            dp[i]=min(dp[i-n]+1, dp[i]);
                        }
                        else{
                            dp[i]= dp[i-n]+1;
                        }
                        
                    }
                }
            }
        }
        return dp[x];


        
    }
};
```
