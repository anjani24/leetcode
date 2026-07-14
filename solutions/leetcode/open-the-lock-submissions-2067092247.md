# open the lock/submissions/2067092247

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:

//bfs shortest path

    int openLock(vector<string>& deadends, string target) {

        int dist=0;
        set<string> mp;

        for(int i=0; i< deadends.size(); i++){
            mp.insert(deadends[i]);
        }

        queue<string> q;
        
        if(mp.find("0000")!=mp.end()){
            return -1;

        }
        q.push("0000");

        while(!q.empty()){

            //layer by layer processing 
            int size= q.size();

            while(size--){

            string V= q.front();
            q.pop();

            if(V == target){
                return dist;
            }

            //forward loop
            for(int i=0; i< 4;i++){
                string neigh = V;
                int num= neigh[i]-'0';
                num = (num+1)%10;
                neigh[i] = num+'0';

                if(mp.find(neigh)!= mp.end()){
                    continue;
                }
                mp.insert(neigh);
                q.push(neigh);
            }

            //backward loop
            for(int i=0; i<4; i++){
                string neigh = V;
                int num = neigh[i]-'0';
                if(num==0){
                    num=9;
                }
                else{
                    num--;
                }
                neigh[i]= num + '0';

                if(mp.find(neigh) != mp.end()){
                    continue;
                }
                mp.insert(neigh);
                q.push(neigh);
            }

            }
            dist++;
            
        }
        return -1;
    }
};
```
