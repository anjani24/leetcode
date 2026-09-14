# rectangle overlap/submissions/2141196168

**Platform:** LeetCode  
**Date:** 2026-09-14  

## Solution

```
class Solution {
public:
    bool isRectangleOverlap(vector<int>& rec1, vector<int>& rec2) {

        int x1 = rec1[0];
        int y1 = rec1[1];
        int x2 = rec1[2];
        int y2 = rec1[3];

        int a1 = rec2[0];
        int b1 = rec2[1];
        int a2 = rec2[2];
        int b2 = rec2[3];

        if(x2<=a1) return false;
        if(y1>=b2) return false;
        if(y2<=b1) return false;
        if(x1>=a2) return false;

        // if(rec2[0]>=rec1[0] && rec2[0]<rec1[2]){
        //     if(rec2[1]>=rec1[1] && rec2[1]< rec1[3]){
        //         return true;
        //     }
        //     if(rec2[3]<=rec1[3] && rec2[3]> rec1[1]){
        //         return true;
        //     }
        //     if(rec2[1]<=rec1[1] && rec2[3]>=rec1[3]){
        //         return true;
        //     }
        // }
        // if(rec2[0]<=rec1[0] && rec2[2]>rec1[0]){
        //     if(rec2[1]>=rec1[1] && rec2[1]< rec1[3]){
        //         return true;
        //     }
        //     if(rec2[3]<=rec1[3] && rec2[3]> rec1[1]){
        //         return true;
        //     }
        //     if(rec2[1]<=rec1[1] && rec2[3]>=rec1[3]){
        //         return true;
        //     }
        // }
        return true;
        
    }
};
```
