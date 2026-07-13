# is graph bipartite/submissions/2065885172

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
class Solution {
public:
    bool isBipartite(vector<vector<int>>& graph) {

        int n= graph.size();
        vector<int> color(n,-1);

        queue<int> q;
        q.push(0);
        color[0]=0;

        while(!q.empty()){
            int V= q.front();
            q.pop();

            for(auto neigh: graph[V]){
                
                if(color[neigh]==-1){
                    color[neigh]= 1- color[V];
                    q.push(neigh);
                }
                else if( color[V]== color[neigh]){
                    return false;
                }
            }

        }
        return true;

        
    }
};
```
