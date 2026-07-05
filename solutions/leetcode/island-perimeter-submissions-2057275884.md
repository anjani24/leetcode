# island perimeter/submissions/2057275884

**Platform:** LeetCode  
**Date:** 2026-07-05  

## Solution

```
class Solution {
public:

    int islandPerimeter(vector<vector<int>>& grid) {

        int m = grid.size();
        int n = grid[0].size();
        int perimeter = 0;

        vector<pair<int, int>> directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
        
        for(int i = 0; i < m; i++) {
            for(int j = 0; j < n; j++) {

                if(grid[i][j]==1){
                    perimeter +=4;

                    for(auto d : directions){
                    int r= i+d.first;
                    int c=j+d.second;

                    if(r>=0 && c>=0 && r<m && c<n && grid[r][c]==1){
                        perimeter--;
                    }
                }
                }

                
                
            }
        }
        return perimeter;   
    }
};
```
