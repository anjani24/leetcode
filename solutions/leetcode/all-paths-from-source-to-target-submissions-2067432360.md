# all paths from source to target/submissions/2067432360

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    void dfs(vector<vector<int>>& graph, vector<int>& current_path, int node, vector<vector<int>> & paths){
        
        int target= graph.size()-1;
        current_path.push_back(node);
        if(node==target){
            paths.push_back(current_path);
        }
        else{

            for(auto neigh: graph[node]){
                dfs(graph, current_path, neigh, paths);
            }

        }
        current_path.pop_back();
    }
    vector<vector<int>> allPathsSourceTarget(vector<vector<int>>& graph) {

        vector<vector<int>> paths;
        int n= graph.size();
        vector<int> current_path;

        dfs(graph, current_path, 0, paths);
        return paths;
    }
};
```
