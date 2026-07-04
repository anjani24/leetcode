# max area of island/submissions/2056137675

**Platform:** LeetCode  
**Date:** 2026-07-04  

## Solution

```
class Solution {
public:
    int dfs(vector<vector<int>>& grid, vector<vector<bool>>& visited, int r, int c){

        int m=grid.size();
        int n=grid[0].size();
        int area=0;
        stack<pair<int,int>> st;
        st.push({r,c});

        while(!st.empty()){

            auto [row,col]= st.top();
            st.pop();

            if(row>=0 && col>=0 && row<m && col<n && visited[row][col]!=true && grid[row][col]==1){
                area++;
                visited[row][col]=true;
                st.push({row+1, col});
                st.push({row-1,col});
                st.push({row, col+1});
                st.push({row, col-1});
            }
        }
        return area;
    }
    int maxAreaOfIsland(vector<vector<int>>& grid) {
        int m= grid.size();
        int n= grid[0].size();
        int ans=0;
        vector<vector<bool>> visited(m, vector<bool>(n,false));

        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){

                if(visited[i][j]==false && grid[i][j]==1){
                    ans= max(ans, dfs(grid, visited, i, j));
                    
                }
            }
        }

        return ans;   
    }
};
```
