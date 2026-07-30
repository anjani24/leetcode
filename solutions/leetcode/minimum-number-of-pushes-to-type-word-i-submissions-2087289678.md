# minimum number of pushes to type word i/submissions/2087289678

**Platform:** LeetCode  
**Date:** 2026-07-30  

## Solution

```
class Solution {
public:
    int minimumPushes(string word) {
        int n= word.size();
        int ans=0;

        for(int i=0; i< n; i++){
            if(i<8){
                ans++;
            }
            else if(i>=8 && i<16){
                ans = ans+2;
            }
            else if(i>=16){
                ans= ans+3;
            }
        }
        return ans;
    }
};
```
