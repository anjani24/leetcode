# M[i,j] --> M'[j,N-1-i]

**Platform:** LeetCode  
**Date:** 2026-09-05  

## Solution

```
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        
        int n= matrix.size();     
        vector<vector<int>> ans (n, vector<int>(n));
        
        // int left=0;
        // int right=n-1;
        // int top=0;
        // int bottom=n-1;
        // int num= n*n;
        // int p=0;
        
        // while(num){
        //     for(int i=left; i<right; i++){
        //         ans[p][right]= matrix[i][top];
                
        //     }
        // }
        
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                ans[j][n-1-i]=matrix[i][j];
            }
        }
        matrix=ans;
    }
};
```
