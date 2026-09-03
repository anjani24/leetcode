# climbing stairs/submissions/2129948523

**Platform:** LeetCode  
**Date:** 2026-09-03  

## Solution

```
class Solution {
public:
    //recurssivie tle O(2^n)
    // int dp(int n, int i){
    //     if(i==1) return 1;
    //     if(i==2) return 2;

    //     return dp(n,i-1)+ dp(n, i-2);
    // }

    //Memoization

    int solve(int n, vector<int>& dp){

        if(n==1) return 1;
        if(n==2) return 2;

        if(dp[n]!=-1){
            return dp[n];
        }

        dp[n]= solve(n-1, dp) +solve(n-2,dp);
        return dp[n];

    }
    int climbStairs(int n) {

        if(n==0) return 0;
        vector<int> dp(n+1,-1);
        return solve(n,dp);
    }
    
};
```
