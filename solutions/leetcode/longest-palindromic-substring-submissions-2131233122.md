# longest palindromic substring/submissions/2131233122

**Platform:** LeetCode  
**Date:** 2026-09-05  

## Solution

```
class Solution {
public:
    string longestPalindrome(string s) {
        
        int n=s.size();
        string r= s;
        reverse(r.begin(),r.end());

        vector<vector<int>>dp(n+1, vector<int>(n+1,0));

        int maxl=0;
        int maxend=0;

        for(int i=1; i<n;i++){
            for(int j=1; j<n;j++){
                if(s[i-1]==r[i-1]){
                    dp[i][j]=dp[i-1][j-1]+1;
                }
                if(dp[i][j]>maxl){
                    maxl= dp[i][j];
                    maxend=i;
                }
            }
        }
        return s.substr(maxend-maxl,maxl);

    }
};
```
