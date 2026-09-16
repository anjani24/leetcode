# number of sets of k non overlapping line segments/submissions/2143389672

**Platform:** LeetCode  
**Date:** 2026-09-16  

## Solution

```
class Solution {
public:
    int numberOfSets(int n, int k) {
        // const int MOD = 1e9 + 7;

        // vector<vector<long long>> dp(
        //     n, vector<long long>(k + 1, 0)
        // );

        // // Zero segments: one way for any prefix
        // for (int i = 0; i < n; i++) {
        //     dp[i][0] = 1;
        // }

        // for (int i = 1; i < n; i++) {
        //     for (int j = 1; j <= k; j++) {
        //         // Do not end a segment at i
        //         dp[i][j] = dp[i - 1][j];

        //         // Choose a segment [p, i]
        //         for (int p = 0; p < i; p++) {
        //             if (j == 1) {
        //                 dp[i][j] += 1;
        //             } else if (p > 0) {
        //                 dp[i][j] += dp[p][j - 1];
        //             }

        //             dp[i][j] %= MOD;
        //         }
        //     }
        // }

        // return dp[n - 1][k];
                const int MOD = 1e9 + 7;

        int N = n + k - 1;
        int R = 2 * k;

        vector<long long> dp(R + 1, 0);
        dp[0] = 1;

        for (int i = 1; i <= N; i++) {
            for (int j = min(i, R); j >= 1; j--) {
                dp[j] = (dp[j] + dp[j - 1]) % MOD;
            }
        }

        return dp[R];
    }
};
```
