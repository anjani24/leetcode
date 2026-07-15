# network delay time/submissions/2068751880

**Platform:** LeetCode  
**Date:** 2026-07-15  

## Solution

```
class Solution {
public:
    int networkDelayTime(vector<vector<int>>& times, int n, int k) {

        vector<vector<pair<int,int>>> adj(n+1); 

        for(auto & edge: times){
            adj[edge[0]].push_back({edge[1],edge[2]});   // 2->[1,1], [3,1]
        }

        vector<int> dist(n+1, INT_MAX);
        dist[k]=0;

        priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pq;
        pq.push({0,k});

        while(!pq.empty()){
            auto [distance, node]= pq.top();
            pq.pop();

            if(distance> dist[node]){
                continue;
            }

            for(auto [neigh,weight]: adj[node]){
                int newDist= distance+ weight;

                if(newDist< dist[neigh]){
                    dist[neigh]=newDist;
                    pq.push({newDist, neigh});
                }
            }
        }
        int maxd=0;

        for(int i=1; i<= n; i++){
            if(dist[i]> maxd){
                maxd=dist[i];
            }
        }

        return maxd==INT_MAX? -1: maxd;







        // vector<vector<pair<int,int>>> adj(n+1);
        // for(auto it: times){
        //     adj[it[0]].push_back({it[1],it[2]});
        // }
        // priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pq;
        // pq.push({0,k});
        // vector<int> dist(n+1, INT_MAX);
        // dist[k]=0;

        // while(!pq.empty()){
        //     auto tp= pq.top();
        //     pq.pop();
        //     int t=tp.first;
        //     int u=tp.second;

        //     for(auto it: adj[u]){
        //         int newt= t+it.second;
        //         if(newt<dist[it.first]){
        //             dist[it.first]= newt;
        //             pq.push({newt, it.first});
        //         }
        //     }
        // }
        // int ans;
        // ans=*max_element(dist.begin()+1,dist.end());

        // return (ans==INT_MAX)?-1:ans;

    }
};
```
