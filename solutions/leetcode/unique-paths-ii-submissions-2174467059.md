# unique paths ii/submissions/2174467059

**Platform:** LeetCode  
**Date:** 2026-10-17  

## Solution

```
class Solution {
public:
    int ans=0;
    void unique(vector<vector<int>>& obstacleGrid, int r, int c){
        int m= obstacleGrid.size();
        int n=obstacleGrid[0].size();
        if(r==m-1 && c==n-1){
            ans++;
            return;
        }
        if(r>=m || c>=n) return;
        if(obstacleGrid[r][c]==1) return;

        //move down
        unique(obstacleGrid, r+1,c);
        //move right
        unique(obstacleGrid, r, c+1);
    }

    int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {

        int m= obstacleGrid.size();
        int n= obstacleGrid[0].size();

        ans=0;

        unique(obstacleGrid, 0,0);

        return ans;
    }
};
```
