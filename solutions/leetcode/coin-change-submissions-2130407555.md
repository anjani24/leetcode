# coin change/submissions/2130407555

**Platform:** LeetCode  
**Date:** 2026-09-04  

## Solution

```
class Solution {
public:
    // int amt(vector<int> & coins, int amount, vector<int> &dp){
    //     if(amount==0) return 0;

    //     if(dp[amount]!=-1){
    //         return dp[amount];
    //     }
    //     int ans
    // }
    int coinChange(vector<int>& coins, int amount) {
        int n=coins.size();
        //min coins needed for every w
        vector<int> dp(amount+1, amount+1);

        //base case
        dp[0]=0;
        
        //unbounded knapsack 
        for(int i=1; i<=amount;i++){
            for(int c:coins){
                if(c<=i){
                    dp[i]= min(dp[i], dp[i-c]+1);

                }
            }
        }
        return dp[amount]==amount+1? -1: dp[amount]; 
    }
};
```
