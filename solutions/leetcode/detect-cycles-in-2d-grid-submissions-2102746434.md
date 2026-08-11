# detect cycles in 2d grid/submissions/2102746434

**Platform:** LeetCode  
**Date:** 2026-08-11  

## Solution

```
class Solution {
public:
    bool dfs(vector<vector<char>>& grid, vector<vector<int>> &visited, int r, int c, int parentrow, int parentcol){
        int n= grid.size();
        int m= grid[0].size();

        visited[r][c]=1;

        vector<int> dr={1,0,0,-1};
        vector<int> dc={0,1,-1,0};
        for(int i=0; i<4; i++){
            int row= dr[i]+r;
            int col= dc[i]+c;
            if(row>=0 && row<n && col>=0 && col<m && grid[row][col]==grid[r][c]){
                if(!visited[row][col]){
                    if(dfs(grid, visited,row,col,r,c)) return true;
                }
                else{
                    if(row==parentrow && col==parentcol){
                        continue;
                    }
                    else{
                        return true;
                    }
                }
            }
        }
        return false;
    }
    bool containsCycle(vector<vector<char>>& grid) {
        int n=grid.size();
        int m=grid[0].size();
        vector<vector<int>>visited(n, vector<int>(m,0));

        for(int i=0; i<n; i++){
            for(int j=0; j<m;j++){
                if(visited[i][j]==0){
                    if(dfs(grid,visited,i,j,-1,-1)) return true;
                }
            }
        }
        return false; 
    }
};
```
