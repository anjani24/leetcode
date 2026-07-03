# number of islands/submissions/2054991370

**Platform:** LeetCode  
**Date:** 2026-07-03  

## Solution

```
class Solution {
public:
    int numIslands(vector<vector<char>>& grid) {

         if (grid.empty()) return 0;
        
        int rows = grid.size();
        int cols = grid[0].size();
        int islands = 0;
        
        for (int r = 0; r < rows; ++r) {
            for (int c = 0; c < cols; ++c) {
                if (grid[r][c] == '1') {
                    islands++;
                    dfs(grid, r, c);
                }
            }
        }
        
        return islands;
    }

private:
    void dfs(std::vector<std::vector<char>>& grid, int r, int c) {
        int rows = grid.size();
        int cols = grid[0].size();
        
        // Base cases: out of bounds or water ('0')
        if (r < 0 || c < 0 || r >= rows || c >= cols || grid[r][c] == '0') {
            return;
        }
        
        // Sink the land to mark it as visited
        grid[r][c] = '0';
        
        // Explore all 4 adjacent directions
        dfs(grid, r + 1, c); // Down
        dfs(grid, r - 1, c); // Up
        dfs(grid, r, c + 1); // Right
        dfs(grid, r, c - 1); // Left
        
        
    }
};
```
