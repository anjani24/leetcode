# dota2 senate/submissions/2131715105

**Platform:** LeetCode  
**Date:** 2026-09-05  

## Solution

```
class Solution {
public:
    string predictPartyVictory(string senate) {

        queue<int> qr;
        queue<int> qd;
        int n= senate.size();

        for(int i=0; i<senate.size();i++){
            if(senate[i]=='R') qr.push(i);
            else{
                qd.push(i);
            } 
        }

        while(!qr.empty() && !qd.empty()){
            int r_idx= qr.front(); qr.pop();
            int d_idx=qd.front(); qd.pop();

            if(r_idx<d_idx){
                qr.push(r_idx+n);
            }
            else{
                qd.push(d_idx+n);
            }
        }
        return !qr.empty()? "Radiant":"Dire";    
    }
};
```
