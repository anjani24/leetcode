# course schedule/submissions/2062660342

**Platform:** LeetCode  
**Date:** 2026-07-10  

## Solution

```
class Solution {
public:
    bool dfscycleDirected(vector<vector<int>>& adj, int node, vector<int> &state){
        state[node]=1; //mark node visited

        for(int neigh : adj[node]){
            if(state[neigh]==1){ return false;}
            if(state[neigh]==0 &&  !dfscycleDirected(adj, neigh, state)){return false;}
            if(state[neigh]==2) continue;
        }
        state[node]=2;
        return true;

    }
    bool canFinish(int numCourses, vector<vector<int>>& prerequisites) {

        //adj list 

        vector<vector<int>> adj(numCourses);
        for(auto p: prerequisites){
            adj[p[1]].push_back(p[0]);
        }

        //3 state dfs
        // state -0 unvisited -1 in current path -2 fully done

        vector<int> state(numCourses, 0);

        for(int i=0; i<numCourses; i++){
            if(state[i]!=2 && !dfscycleDirected(adj, i , state)){
                return false;
            }
        }
        return true;
   
    }
};
```
