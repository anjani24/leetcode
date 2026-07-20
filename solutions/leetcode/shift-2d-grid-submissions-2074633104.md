# shift 2d grid/submissions/2074633104

**Platform:** LeetCode  
**Date:** 2026-07-20  

## Solution

```
class Solution {
public:
    vector<vector<int>> shiftGrid(vector<vector<int>>& grid, int k) {
        int m= grid.size();
        int n= grid[0].size();

        while(k){
            int a= grid[m-1][n-1];
            for(int i=0; i<m ; i++){
                for(int j=0; j<n ;j++){
                    swap(grid[i][j], grid[0][0]);
                }
            }
            k--;
        }
        return grid;
    }
};
```
