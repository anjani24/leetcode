# possible bipartition/submissions/2065877265

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
class Solution {
public:
    bool isbipartite(int V, vector<vector<int>>& adj, vector<int> &color){

        queue<int> q;
        q.push(V);
        color[V]=0;

        while(!q.empty()){
            int V= q.front();
            q.pop();

            for(auto neigh : adj[V]){
                if(color[neigh]==color[V]){
                    return false;
                }
                else if(color[neigh]==-1){
                    color[neigh]= 1-color[V];
                    q.push(neigh);
                }
            }
        }
        return true;
    }

    bool possibleBipartition(int n, vector<vector<int>>& dislikes) {

        vector<vector<int>> adj(n+1);

        for(int i=0; i<dislikes.size(); i++){
            adj[dislikes[i][0]].push_back(dislikes[i][1]);
            adj[dislikes[i][1]].push_back(dislikes[i][0]);
        }

        vector<int> color(n+1,-1);


        for(int i=1; i<=n; i++){
            if(color[i]==-1){
                if(!isbipartite(i, adj, color)){
                    return false;
                }
            }
        }
        return true;    
    }
};
```
