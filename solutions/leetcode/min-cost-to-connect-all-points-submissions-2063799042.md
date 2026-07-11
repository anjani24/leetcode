# min cost to connect all points/submissions/2063799042

**Platform:** LeetCode  
**Date:** 2026-07-11  

## Solution

```
class Solution {
public:
    int minCostConnectPoints(vector<vector<int>>& points) {
        int n=points.size();
        vector<int> minDis(n,INT_MAX);
        vector<bool> inMST(n, false);
        minDis[0]=0;
        int totalCost=0;

        for(int i=0; i<n;i++){

            int u=-1;
            for(int v=0; v<n;v++){
                if(!inMST[v]&& (u==-1 || minDis[v]<minDis[u])){
                    u=v;
                }
            }

            inMST[u]=true;
            totalCost+= minDis[u];

            for(int v=0; v<n;v++){
                if(!inMST[v]){
                    int dist= abs(points[u][0]-points[v][0]) + abs(points[u][1]- points[v][1]);
                    minDis[v]= min(dist, minDis[v]);
                }
            }
            
        }
        return totalCost;

        
        
    }
};
```
