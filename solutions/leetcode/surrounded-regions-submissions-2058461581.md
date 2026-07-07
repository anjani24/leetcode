# surrounded regions/submissions/2058461581

**Platform:** LeetCode  
**Date:** 2026-07-07  

## Solution

```
class Solution {
public:
    void dfs( int i, int j, int n, int m, vector<vector<char>>& board,vector<vector<int>>& visited ){
        visited[i][j]=1;
        int x[]={-1,0,1,0};
        int y[]={0,1,0,-1};
        for(int p=0; p<4;p++){
            int ni= x[p]+ i;
            int nj=y[p]+j;
            if( ni>=1 && nj>=1 && ni<m-1 && nj<n-1 && board[ni][nj]=='O' && visited[ni][nj]==0){
                    
                    dfs( ni,nj, n,m, board, visited);
            
            }
        }


    }
    void solve(vector<vector<char>>& board) {
        int m= board.size();
        int n= board[0].size();
        vector<vector<int>> visited(m,vector<int>(n,0));
        for(int i=0;i<m;i++)
        {
            if(board[i][0]=='O')dfs(i,0,n,m,board,visited);
            if(board[i][n-1]=='O')dfs(i,n-1,n,m,board,visited);
        }
        for(int i=0;i<n;i++)
        {
            if(board[0][i]=='O')dfs(0,i,n,m,board,visited);
            if(board[m-1][i]=='O')dfs(m-1,i,n,m,board,visited);
        }
        
        for( int i=0; i<m ;i++){
            for(int j=0; j<n ;j++){
                if(board[i][j]=='O'&& visited[i][j]==0){
                    board[i][j]='X';
                }
                
            }
        }     
    }
};
```
