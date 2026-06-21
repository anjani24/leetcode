# set matrix zeroes/description

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int m= matrix.size();
        int n= matrix[0].size();
        queue<pair<int, int>> q;
        vector<vector<int>> ans= matrix;
        for(int i=0; i<m;i++){
            for(int j=0;j<n;j++){
                if(matrix[i][j]==0){
                    q.push({i,j});
                }
            }
        }
        while(!q.empty()){
            pair<int, int> a= q.front();
            for(int i=0; i< m;i++){
                matrix[i][a.second]=0;      
            }
            for(int i=0; i< n;i++){
               matrix[a.first][i]=0;     
            }   
            q.pop();
        }
        
    }
};
```
