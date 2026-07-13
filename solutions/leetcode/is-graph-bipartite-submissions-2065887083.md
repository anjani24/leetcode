# is graph bipartite/submissions/2065887083

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
class Solution {
public:
    bool isBipartite(vector<vector<int>>& graph) {

        int n= graph.size();
        vector<int> color(n,-1);

        for(int i=0; i<n ;i++){
            if(color[i]!=-1) continue;
            queue<int> q;
            q.push(i);
            color[i]=0;

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

        }
        return true;

        
    }
};
```
