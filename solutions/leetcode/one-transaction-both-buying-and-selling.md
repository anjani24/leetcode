# One transaction = both buying and selling

**Platform:** LeetCode  
**Date:** 2026-10-17  

## Solution

```
class Solution {
public:
    int maxProfit(vector<int>& prices, int fee) {

        int n= prices.size();

        vector<int> state1(n,0); //for holding a stock -- 2 options- do nothing, sell
        vector<int> state2(n,0); //not holding options-- buy or do nthign

        state1[0]=0;
        state2[0]= -prices[0];

        for(int i=1; i<n;i++){
            state1[i]= max(state1[i-1],state2[i-1]+prices[i]-fee); //keep holding ,buy today

            state2[i]= max(state2[i-1], state1[i-1]-prices[i]);
        }
        return state1[n-1];
    }
};

//eod ki states hai ye
```
