# cinema seat allocation/submissions/2113054333

**Platform:** LeetCode  
**Date:** 2026-08-19  

## Solution

```
#include <vector>
#include <unordered_map>

using namespace std;

class Solution {
public:
    int maxNumberOfFamilies(int n, vector<vector<int>>& reservedSeats) {
        // Map: Row number -> A structure tracking if our 3 family zones are blocked
        // Index 0: Left block blocked? (seats 2-5)
        // Index 1: Middle block blocked? (seats 4-7)
        // Index 2: Right block blocked? (seats 6-9)
        unordered_map<int, vector<bool>> row_blocks;
        
        for (const auto& seat : reservedSeats) {
            int row = seat[0];
            int col = seat[1];
            
            // If the row hasn't been seen yet, initialize its 3 blocks as 'false' (unblocked)
            if (row_blocks.find(row) == row_blocks.end()) {
                row_blocks[row] = {false, false, false};
            }
            
            // Mark which structural blocks are ruined by this seat
            if (col >= 2 && col <= 5) row_blocks[row][0] = true; // Blocks Left
            if (col >= 4 && col <= 7) row_blocks[row][1] = true; // Blocks Middle
            if (col >= 6 && col <= 9) row_blocks[row][2] = true; // Blocks Right
        }
        
        // Rows with no reservations automatically fit 2 families each
        int count = (n - row_blocks.size()) * 2;
        
        // Process only the rows that have reservations
        for (const auto& [row, blocks] : row_blocks) {
            bool left_blocked = blocks[0];
            bool middle_blocked = blocks[1];
            bool right_blocked = blocks[2];
            
            if (!left_blocked && !right_blocked) {
                count += 2; // Both left and right blocks are perfectly free
            } else if (!left_blocked || !right_blocked || !middle_blocked) {
                count += 1; // At least one valid configuration fits
            }
        }
        
        return count;
    }
};

```
