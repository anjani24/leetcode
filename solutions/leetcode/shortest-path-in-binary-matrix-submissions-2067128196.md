# shortest path in binary matrix/submissions/2067128196

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    int shortestPathBinaryMatrix(vector<vector<int>>& grid) {

        int n=grid.size();

        if(grid[0][0]==1 || grid[n-1][n-1]==1){
            return -1;
        }

        int dist=1;

        vector<vector<bool>> visited(n, vector<bool>(n, false));

        vector<int> dr= {-1,-1,-1,0,0,1,1,1};
        vector<int> dc= {-1,0,1,-1,1,-1,0,1};

        queue<pair<int, int>> q;
        q.push({0,0});

        while(!q.empty()){
            int size= q.size();

            while(size--){
                auto [r,c]= q.front();
                q.pop();

                if(r==n-1 && c==n-1){
                    return dist;
                }

                for(int i=0; i<8; i++){
                    int row= r+ dr[i];
                    int col= c+ dc[i];

                    if(row>=0 && row< n && col>=0 && col<n && grid[row][col]==0 && !visited[row][col]){
                        visited[row][col]=true;
                        q.push({row,col});
                    }
                }
            }
            dist++;
        }
        return -1;































        // int n=grid.size();
        // if(grid[0][0]==1||grid[n-1][n-1]==1){
        //     return -1;
        // }

        // int dr[]={-1,-1,-1,0,1,1,1,0};
        // int dc[]={-1,0,1,1,1,0,-1,-1};

        // queue<pair<int,int>> q;
        // q.push({0,0});
        // grid[0][0]=1; //store dist in grid
        // while(!q.empty()){
        //     auto[r,c]=q.front();
        //     q.pop();
        //     int dist= grid[r][c];
        //     if(r==n-1&& c==n-1){return dist;}
        //     for(int i=0;i<8;i++){
        //         int nr=dr[i]+r;
        //         int nc=dc[i]+c;
        //         if(nr>=0&&nc>=0&&nr<n&&nc<n&&grid[nr][nc]==0){
        //             grid[nr][nc]=dist+1;
        //             q.push({nr,nc});
        //         }
        //     }
        // }
        // return -1;   
    }
};
```
