# minimum height trees/submissions/2066059292

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
class Solution {
public:
    vector<int> findMinHeightTrees(int n, vector<vector<int>>& edges) {

        vector<int>degree(n,0);

        for(int i=0; i< edges.size();i++){
            degree[edges[i][0]]++;
            degree[edges[i][1]]++;
        }

        vector<int> ans;
        int a=0;

        for(int i=0; i<n;i++){
            if(degree[i]==1){
                a++;
            }
        }
        if(a==n){return edges[0];}
        
        for(int i=0; i<n; i++){
            if(degree[i]>1){
                ans.push_back(i);
            }
        }
        return ans;
        
    }
};
```
