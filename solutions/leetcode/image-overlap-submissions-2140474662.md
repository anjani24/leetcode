# image overlap/submissions/2140474662

**Platform:** LeetCode  
**Date:** 2026-09-13  

## Solution

```
class Solution {
public:
    int largestOverlap(vector<vector<int>>& img1, vector<vector<int>>& img2) {

        int n= img1.size();
        map<pair<int,int>,int>mp;

        for(int i=0; i<n;i++){
            for(int j=0; j<n;j++){
                if(img1[i][j]==0) continue;

                for(int r=0; r<n; r++){
                    for(int c=0; c<n;c++){
                        if(img2[r][c]==1){
                            mp[{r-i, c-j}]++;
                        }
                    }
                }
            }
        }

        int ans=0;

        for(auto& m: mp){
            if(m.second>ans){
                ans=m.second;
            }
        }
        return ans;
       
    }
};
```
