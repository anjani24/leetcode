# rectangle overlap/submissions/2141183694

**Platform:** LeetCode  
**Date:** 2026-09-14  

## Solution

```
class Solution {
public:
    bool isRectangleOverlap(vector<int>& rec1, vector<int>& rec2) {

        if(rec2[0]>=rec1[0] && rec2[0]<rec1[2]){
            if(rec2[1]>=rec1[1] && rec2[1]< rec1[3]){
                return true;
            }
        }
        return false;
        
    }
};
```
