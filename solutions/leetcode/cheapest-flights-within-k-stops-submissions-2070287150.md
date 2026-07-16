# cheapest flights within k stops/submissions/2070287150

**Platform:** LeetCode  
**Date:** 2026-07-16  

## Solution

```
class Solution {
public:
    int findCheapestPrice(int n, vector<vector<int>>& flights, int src, int dst, int k) {

        vector<vector<pair<int,int>>> adj(n);
        for(auto f: flights){
            adj[f[0]].push_back({f[1], f[2]});
        }

        vector<int> dist(n,INT_MAX);

        priority_queue< tuple<int,int,int>, vector<tuple<int,int, int>>, greater<tuple<int,int,int>>> pq;
        pq.push({0, src,0});

        while(!pq.empty()){
            auto [price, node, stops]= pq.top();
            pq.pop();

            if(node==dst){
                return price;
            }

            if(stops<=k){
                for( auto [neigh, p]: adj[node]){
                    int newp = price+p;
                    if(newp < dist[neigh]){
                        dist[neigh]= newp;
                        pq.push({newp, neigh, stops+1});
                    }
                }
            }
        }
        return -1;























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
