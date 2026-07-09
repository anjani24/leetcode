# Hint

**Platform:** LeetCode  
**Date:** 2026-07-09  

## Solution

```
class Solution {
public:
    int maxDistance(vector<vector<int>>& grid) {
        int n= grid.size();
        queue<pair<int, int>> q;
        int ans=-1;
        int land=0;
        int water=0;
        vector<vector<bool>> visited(n, vector<bool>(n, false));

        for(int i=0; i<n ;i++){
            for(int j=0; j<n; j++){
                if(grid[i][j]==1){
                    q.push({i,j});
                    visited[i][j]=true;
                }
                if(grid[i][j]==1){
                    land++;
                }
                if(grid[i][j]==0){
                    water++;
                }
            }
        }
        if(land==0 || water==0){
            return -1;
        }

        vector<pair<int, int>> dir= {{1,0},{-1,0},{0,1}, {0,-1}};

        while(!q.empty()){
            int size= q.size();
            while(size--){
                auto [r,c]= q.front();
                q.pop();
                

                for(auto [x,y]: dir){
                    int i= x+r;
                    int j= y+c;
                    if(i>=0 && j>=0 && i<n && j<n && visited[i][j]!=true && grid[i][j]==0 ){
                        visited[i][j]=true;
                        grid[i][j]=1;
                        q.push({i,j});
                    }
                }
            }
            ans++;
        }
        return ans;
    }
};
```
