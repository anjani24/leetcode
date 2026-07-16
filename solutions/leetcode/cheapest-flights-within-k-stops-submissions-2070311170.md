# cheapest flights within k stops/submissions/2070311170

**Platform:** LeetCode  
**Date:** 2026-07-16  

## Solution

```
class Solution {
public:
    int findCheapestPrice(int n, vector<vector<int>>& flights, int src, int dst, int k) {

        vector<int> dist(n, INT_MAX);
        dist[src] = 0;

        // k stops allowed => at most k+1 edges => k+1 rounds of relaxation
        for (int round = 0; round <= k; round++) {
            vector<int> temp = dist; // snapshot from PREVIOUS round only

            for (auto& f : flights) {
                int u = f[0], v = f[1], price = f[2];
                if (dist[u] != INT_MAX && dist[u] + price < temp[v]) {
                    temp[v] = dist[u] + price;
                }
            }
            dist = temp; // commit this round's results
        }

        return dist[dst] == INT_MAX ? -1 : dist[dst];
    
























        // if(src==dst){
        //     return 0;
        // }
        // vector<vector<pair<int,int>>>adj(n);
        // for(auto it: flights){
        //     adj[it[0]].push_back({it[1], it[2]});
        // }
        // priority_queue<vector<int>, vector<vector<int>>, greater<vector<int>>> pq;
        // pq.push({0,src,0});
        // vector<vector<int>> dist(n, vector<int>(k+2,1e9));
        // dist[src][0]=0;
        // while(!pq.empty()){
        //     auto top= pq.top();
        //     pq.pop();
        //     int p=top[0];
        //     int to=top[1];
        //     int stops=top[2];
        //     if(to==dst){
        //         return p;
        //     }
        //     if(stops<=k){
        //        for(auto& it: adj[to]){
        //         int price=it.second;
        //         int v=it.first;
        //         int newp= price+p;
        //         if(newp<dist[v][stops+1]){
        //             dist[v][stops+1]=newp;
        //             pq.push({p+price,v, stops+1});
        //         }
                
        //        }
        //     }
        // }
        // return -1;        
    }
};
```
