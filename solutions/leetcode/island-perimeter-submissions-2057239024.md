# island perimeter/submissions/2057239024

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
        
        for(int i = 0; i < m; ++i) {
            for(int j = 0; j < n; ++j) {
                if(grid[i][j] == 1) {
                    perimeter += 4; // Assume 4 sides initially
                    
                    for(auto dir : directions) {
                        int ni = i + dir.first;
                        int nj = j + dir.second;
                        
                        // Check if the adjacent cell is also land
                        if(ni >= 0 && ni < m && nj >= 0 && nj < n && grid[ni][nj] == 1) {
                            perimeter--; // Subtract 1 for each shared border
                        }
                    }
                }
            }
        }
        return perimeter;

        
    }
};
```
