# rotting oranges/submissions/2059649566

**Platform:** LeetCode  
**Date:** 2026-07-07  

## Solution

```
class Solution {
public:
    void bfs(vector<vector<int>> & grid, vector<vector<bool>>&visited, int &ans, queue<pair<int,int>>& q){
        int m= grid.size();
        int n=grid[0].size();
        
        while(!q.empty()){
            
            int size=q.size();
            while(size>0){
                size--;
                auto [r,c]= q.front();
                q.pop();
                visited [r][c]=true;

                int dr[] = {-1, 1, 0, 0};
                int dc[] = {0, 0, -1, 1};

                for (int dir = 0; dir < 4; dir++) {
                    int nr = r + dr[dir];
                    int nc = c + dc[dir];

                    if (nr >= 0 && nc >= 0 && nr < m && nc < n && grid[nr][nc] == 1 && !visited[nr][nc]){
                        grid[nr][nc]=2;
                        q.push({nr,nc});

                    }
                 }
            }
            if(q.size()>0){
                ans++;
            }
        }
    }
    int orangesRotting(vector<vector<int>>& grid) {

        int m= grid.size();
        int n= grid[0].size();
        int ans=0;
        vector<vector<bool>> visited(m, vector<bool>(n,false));
        queue<pair<int,int>> q;

        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){
                if(visited[i][j]==false && grid[i][j]==2){
                    q.push({i,j});
                }
            }
        }
        bfs(grid, visited, ans, q);

        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){
                if(grid[i][j]==1){
                    return -1;
                }
            }
        }
        return ans;
        
    }
};
```
