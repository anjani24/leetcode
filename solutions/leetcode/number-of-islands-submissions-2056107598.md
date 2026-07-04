# number of islands/submissions/2056107598

**Platform:** LeetCode  
**Date:** 2026-07-04  

## Solution

```
class Solution {
public:

    void dfs(vector<vector<char>>& grid, vector<vector<bool>>& visited, int r, int c){
        int m= grid.size();
        int n= grid[0].size();
        stack<pair<int, int>> s;
        s.push({r,c});

        while(!s.empty()){
            auto [r,c]= s.top();
            s.pop();

            if(r>=0 && c>=0 && r<m && c<n && grid[r][c]=='1' && visited[r][c] != true){
                visited[r][c]=true;
                s.push({r+1,c});
                s.push({r-1,c});
                s.push({r,c+1});
                s.push({r,c-1});
            }
        }
        
        // if(r>=0 && c>=0 && r<m && c<n && grid[r][c]=='1' && visited[r][c] != true){
        //     visited[r][c]=true;
        
        //     dfs(grid, visited, r+1,c);
        //     dfs(grid, visited, r-1,c);
        //     dfs(grid, visited, r,c+1);
        //     dfs(grid, visited, r,c-1);
        // }

    }

    int numIslands(vector<vector<char>>& grid) {

        int m= grid.size();
        int n=grid[0].size();
        int count=0;
        vector<vector<bool>> visited(m, vector<bool>(n,false));
        
        for(int i=0; i<m;i++){
            for(int j=0; j<n; j++){
                if(!visited[i][j] && grid[i][j]!='0'){
                    dfs(grid, visited,i, j);
                    count++;
                }
            }
        }
        return count;        
    }
};
```
