# unique paths ii

**Platform:** LeetCode  
**Date:** 2026-10-17  

## Solution

```
class Solution {
public:
    // int ans=0;
    // void unique(vector<vector<int>>& obstacleGrid, int r, int c){
    //     int m= obstacleGrid.size();
    //     int n=obstacleGrid[0].size();
    //     if(r>=m || c>=n) return;
    //     if(obstacleGrid[r][c]==1) return;
    //     if(r==m-1 && c==n-1){
    //         ans++;
    //         return;
    //     }

    //     //move down
    //     unique(obstacleGrid, r+1,c);
    //     //move right
    //     unique(obstacleGrid, r, c+1);
    // }

    // int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {

    //     int m= obstacleGrid.size();
    //     int n= obstacleGrid[0].size();

    //     ans=0;

    //     unique(obstacleGrid, 0,0);

    //     return ans;
    // }

    //memoization

    int unique(vector<vector<int>>& obstacleGrid, vector<vector<int>>& dp, int r, int c){

        int m= obstacleGrid.size();
        int n= obstacleGrid[0].size();

        if(r<0 || c<0) return 0;
        
        if(obstacleGrid[r][c]==1){
            dp[r][c]=0;
            return 0;
        }

        if(r==0 && c==0) return 1;

        if(dp[r][c]!=-1) dp[r][c];

        int up= unique(obstacleGrid, dp, r-1, c);
        int left= unique(obstacleGrid, dp, r, c-1);

        return dp[r][c]= up+left;

        
    }

    int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {

        int m= obstacleGrid.size();
        int n= obstacleGrid[0].size();

        vector<vector<int>> dp(m, vector<int>(n,0));

        return unique(obstacleGrid, dp, m-1, n-1);
    }


};
```
