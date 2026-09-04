# coin change ii/submissions/2130455663

**Platform:** LeetCode  
**Date:** 2026-09-04  

## Solution

```
class Solution {
public:
    int change(int amount, vector<int>& coins) {

        int n= coins.size();
        vector<unsigned int> dp(amount+1, 0);
        //base case
        dp[0]=1;
        for(int c: coins){
            for(int i=c; i<amount+1; i++){

                dp[i]+=dp[i-c];
            }
        }
        return dp[amount];
        
    }
};
```
