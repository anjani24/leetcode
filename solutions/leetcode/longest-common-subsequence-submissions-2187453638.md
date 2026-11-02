# longest common subsequence/submissions/2187453638

**Platform:** LeetCode  
**Date:** 2026-11-02  

## Solution

```
class Solution {
public:
    int longestCommonSubsequence(string text1, string text2) {
        // int m=text2.length();
        // int n=text1.length();
        // vector<vector<int>>t(m+1,vector<int>(n+1,0));

        // for(int i=0;i<m+1;i++)
        // {
        //     for(int j=0;j<n+1;j++)
        //     {
        //         if(i==0||j==0)
        //         {
        //             t[i][j]=0;
        //         }

        //     }
        // }
        // for(int i=1;i<m+1;i++)
        // {
        //     for(int j=1;j<n+1;j++)
        //     {
        //         if(text2[i-1]==text1[j-1])
        //         {
        //             t[i][j]=t[i-1][j-1]+1;
        //         }
        //         else
        //         t[i][j]=max(t[i][j-1],t[i-1][j]);

        //     }
        // }
        // return t[m][n];


        //dp

        int m=text1.size();
        int n=text2.size();

        vector<vector<int>>dp (m+1, vector<int>(n+1, 0) );

        for(int i=1; i< m+1; i++){
            for(int j=1; j<n+1; j++){

                if(text1[i-1]==text2[j-1]){
                    dp[i][j]= dp[i-1][j-1]+1;
                }
                else{
                    dp[i][j]= max(dp[i-1][j], dp[i][j-1]);
                }

            }
        }
        return dp[m][n];
    }
};
```
