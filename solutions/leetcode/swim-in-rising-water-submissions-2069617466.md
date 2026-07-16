# swim in rising water/submissions/2069617466

**Platform:** LeetCode  
**Date:** 2026-07-16  

## Solution

```
class Solution {
public:
    int swimInWater(vector<vector<int>>& grid) {

        int n= grid.size();
        int dr[]= {-1,0,1,0};
        int dc[]= {0,1,0,-1};

        vector<vector<bool>> visited(n, vector<bool>(n, false));
        visited[0][0]=true;

        priority_queue<pair<int, pair<int,int>>, vector<pair<int, pair<int,int>>>, greater<pair<int, pair<int,int>>>> pq;

        pq.push({grid[0][0], {0,0}});

        while(!pq.empty()){
            auto [time,pos] = pq.top();
            pq.pop();
            int r= pos.first;
            int c=pos.second;

            if(r==n-1 && c==n-1){
                return time;
            }

            for(int i=0; i<4; i++){
                int row= r+dr[i];
                int col= c+dc[i];

                if(row>=0 && col>=0 && row<n && col<n && !visited[row][col]){
                    visited[row][col]=true;
                    int next_time= max(time, grid[row][col]);
                    pq.push({next_time,{row,col}});

                }
            }
        }
        return grid[n-1][n-1];        
    }
};
```
