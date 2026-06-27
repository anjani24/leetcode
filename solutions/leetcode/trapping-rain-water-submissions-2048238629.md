# trapping rain water/submissions/2048238629

**Platform:** LeetCode  
**Date:** 2026-06-27  

## Solution

```
class Solution {
public:
    int trap(vector<int>& height) {

        int n= height.size();
        int l=0; 
        int r=n-1;
        int maxl=0;
        int maxr=0;
        int water=0;

        while(l< r){

            if(height[l]> height[r]){
                maxr= max(maxr, height[r]);
                water += maxr- height[r];
                r--;
            }
            else{
                maxl= max(maxl, height[l]);
                water += maxl -height[l];
                l++;
            }
        }
        return water;

    }
};
```
