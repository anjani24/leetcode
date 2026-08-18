# zigzag conversion/submissions/2111286167

**Platform:** LeetCode  
**Date:** 2026-08-18  

## Solution

```
class Solution {
public:
    string convert(string s, int numRows) {
        
        if(numRows<=1) return s;

        int start= (numRows*2)-2;
        int si= s.size();
        string ans(si,' ');
        int j=0;
        int p=0;
        int fin=start;

        while(numRows--){
            int i=p;
            
            for(i=p; i<si; i+=fin){
                ans[j]=s[i];
                j++;

                if(fin!=start && i+start<si && start!=0){
                    ans[j]=s[i+start];
                    j++;
                }
            }
            p++;
            start=start-2;

        }
        return ans;
        
    }
};
```
