# climbing stairs/submissions/2129958389

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

    // int solve(int n, vector<int>& dp){

    //     if(n==1) return 1;
    //     if(n==2) return 2;

    //     if(dp[n]!=-1){
    //         return dp[n];
    //     }

    //     dp[n]= solve(n-1, dp) +solve(n-2,dp);
    //     return dp[n];
    //}
    int climbStairs(int n) {

        if(n<=2) return n;
        // vector<int> dp(n+1);
        // dp[1]=1;
        // dp[2]=2;
        int prev1=1;
        int prev2=2;

        for(int i=3; i<n+1; i++){

            // dp[i]=dp[i-1]+dp[i-2];
            int curr= prev1+prev2;
            prev2= prev1;
            prev1= curr;
        }
        
        return prev1;
    }
    
};
```
