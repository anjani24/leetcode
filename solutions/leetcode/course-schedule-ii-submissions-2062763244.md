# course schedule ii/submissions/2062763244

**Platform:** LeetCode  
**Date:** 2026-07-10  

## Solution

```
class Solution {
public:
    bool dfs(vector<vector<int>> &adj, int node, stack<int> & result, vector<int> & state){
        state[node]=1;

        for(auto n: adj[node]){
            if(state[n]==1){return false;}
            if(state[n]==0 && !dfs(adj, n, result, state)){ return false;   
            }

        }
        state[node]=2;
        result.push(node);
        return true;

    }
    vector<int> findOrder(int numCourses, vector<vector<int>>& pre) {
        vector<int> order;

        vector<vector<int>> adj(numCourses);
        for(auto p:pre){
            adj[p[1]].push_back(p[0]);
        }

        vector<int> state( numCourses, 0);
        stack<int> result;

        for(int i=0; i< numCourses; i++){
            if(state[i]!= 2 && !dfs(adj, i, result, state)){
                return {};
            }
        }

        while(!result.empty()){
            order.push_back(result.top());
            result.pop();
        }
        return order;
        










        // vector<vector<int>> adj(numCourses);
        // int m=pre.size();
        // vector<int>indegree(numCourses,0);
        // for(int i=0;i<m;i++)
        // {
        //     adj[pre[i][1]].push_back(pre[i][0]);
        //     indegree[pre[i][0]]++;
        // }

        // queue<int>q;
        // vector<int>ans;
        // for(int i=0;i<indegree.size();i++)
        // {
        //     if(indegree[i]==0)
        //     {
        //         q.push(i);
        //     }
        // }
        // while(!q.empty())
        // {int x=q.front();
        // q.pop();
        //     ans.push_back(x);
        // for(int node:adj[x])
        //     {
        //         indegree[node]--;
        //     if(indegree[node]==0)q.push(node);
        //     }
            
        // }
        // if(ans.size()==numCourses)return ans;
        // else return {};
    }
        
};
```
