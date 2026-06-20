# counting bits/submissions/2039711434

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int> ans(n+1);

        for(int i=0; i<=n;i++){
            int count=0;
            int p= i;

            while(p){
                count += p%2;
                p = p>>1;
            }
            ans[i]= count;

        }
        return ans;
        
    }
};
```
