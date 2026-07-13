# minimum height trees/submissions/2066260616

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
class Solution {
public:
    vector<int> findMinHeightTrees(int n, vector<vector<int>>& edges) {

        if(n==1){return {0};}

        vector<int>degree(n,0);
        vector<vector<int>> adj(n);
        queue<int> q;


        for(int i=0; i<edges.size() ;i++){
            adj[edges[i][0]].push_back(edges[i][1]);
            adj[edges[i][1]].push_back(edges[i][0]);
            degree[edges[i][0]]++;
            degree[edges[i][1]]++;
        }

        for(int i=0; i<n; i++){
            if(degree[i]==1){
                q.push(i);
            }
        }
        vector<int> ans;

        int remainingNodes= n;


        while(remainingNodes>2){
            int layerSize = q.size();
            remainingNodes -=layerSize;

            for(int i=0; i< layerSize; i++){

                int V= q.front();
                q.pop();
            
            for(auto neigh: adj[V]){
                degree[neigh]--;

                if(degree[neigh]==1){
                    q.push(neigh);
                }
            }
            }
        }

        while(!q.empty()){
            ans.push_back(q.front());
            q.pop();
        }
        return ans;   
    }
};
```
