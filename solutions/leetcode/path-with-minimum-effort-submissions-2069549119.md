# path with minimum effort/submissions/2069549119

**Platform:** LeetCode  
**Date:** 2026-07-16  

## Solution

```
class Solution {
public:
    int minimumEffortPath(vector<vector<int>>& heights) {

        int m= heights.size();
        int n= heights[0].size();
        vector<vector<int>> diff(m, vector<int>(n, INT_MAX));
        diff[0][0]=0;

        vector<int> dr={ -1,0,1,0};
        vector<int> dc={ 0,1,0,-1};

        priority_queue< pair<int, pair<int,int>>, vector<pair<int, pair<int,int>>>, greater<pair<int, pair<int,int>>>>pq;

        pq.push({0,{0,0}});

        while(!pq.empty()){
            auto [d, pos]= pq.top();
            pq.pop();
            int r= pos.first;
            int c= pos.second;

            if(r==m-1 && c==n-1){
                return d;
            }

            for(int i=0; i<4;i++){
                int row= r + dr[i];
                int col= c + dc[i];
                

                if(row>=0 && col>=0 && row<m && col<n){
                    int neweff= max(d, abs(heights[row][col]-heights[r][c]));
                    if(neweff<diff[row][col]){
                        diff[row][col]= neweff;
                        pq.push({neweff,{row,col}});
                    }  
                }
            }
        }

        return 0;





        // int n= heights.size();
        // int m= heights[0].size();
        // int dr[]={-1,0,1,0};
        // int dc[]={0,1,0,-1};

        // vector<vector<int>> diff(n,vector<int>(m,INT_MAX));
        // diff[0][0]=0;

        // if(n-1==0&&m-1==0){
        //     return 0;
        // }

        // priority_queue<pair<int,pair<int,int>>,vector<pair<int,pair<int,int>>>,greater<pair<int,pair<int,int>>>> pq;
        // pq.push({0,{0,0}});

        // while(!pq.empty()){
        //     auto[d,pos]=pq.top();
        //     pq.pop();
        //     int r=pos.first;
        //     int c=pos.second;
        //     if(r==n-1&&c==m-1){
        //         return d;
        //     }
        //     for(int i=0;i<4;i++){
        //         int nr=r+dr[i];
        //         int nc=c+dc[i];
        //         if(nr<n&&nc<m&&nr>=0&&nc>=0){
        //             int neff=max(d, abs(heights[nr][nc]-heights[r][c]));
        //             if(neff<diff[nr][nc]){
        //             diff[nr][nc]=neff;
        //             pq.push({neff,{nr,nc}});
        //             }
        //         }              
        //     }
        // }
        // return 0; 
    }
};
```
