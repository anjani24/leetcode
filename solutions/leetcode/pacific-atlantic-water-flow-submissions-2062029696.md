# pacific atlantic water flow/submissions/2062029696

**Platform:** LeetCode  
**Date:** 2026-07-09  

## Solution

```
class Solution {
public:
    vector<vector<int>> pacificAtlantic(vector<vector<int>>& heights) {
        int m= heights.size();
        int n= heights[0].size();
        vector<vector<int>> ans;
        vector<vector<int>> pacific(m, vector<int>(n,0));

        queue<pair<int,int>> q;
        
        for(int i=0; i< n ; i++){
            q.push({0,i});
            pacific[0][i]++;
        }
        for(int i=0; i<m;i++){
            q.push({i,0});
            pacific[i][0]++;
        }
        // queue has all pacific edge cells

        vector<pair<int,int>> dir= {{1,0}, {0,1},{-1,0},{0,-1}};

        while(!q.empty()){
            auto[r,c]= q.front();
            q.pop();

            for(auto [rd,cd]: dir){
                int rr= r+rd;
                int cc= c+ cd;

                if(rr>=0 && rr<m && cc>=0 && cc<n && pacific[rr][cc]==0 && heights[rr][cc]>=heights[r][c]){
                    pacific[rr][cc]++;
                    q.push({rr,cc});
                }
            }
        }


        vector<vector<int>> atlantic(m, vector<int>(n,0));

        for(int i=0; i< n ; i++){
            q.push({m-1,i});
            atlantic[m-1][i]++;
        }
        for(int i=0; i<m;i++){
            q.push({i,n-1});
            atlantic[i][n-1]++;
        }

        // queue has all atlantic edge cells

        while(!q.empty()){
            auto[r,c]= q.front();
            q.pop();

            for(auto [rd,cd]: dir){
                int rr= r+rd;
                int cc= c+cd;

                if(rr>=0 && rr<m && cc>=0 && cc<n && atlantic[rr][cc]==0 && heights[rr][cc]>=heights[r][c]){
                    atlantic[rr][cc]++;
                    q.push({rr,cc});
                }
            }
        }

        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){
                if(pacific[i][j]>=1 && atlantic[i][j]>=1){
                    ans.push_back({i,j});
                }

            }
        }
        return ans; 
    }
};
```
