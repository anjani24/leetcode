# reverse degree of a string/submissions/2147541520

**Platform:** LeetCode  
**Date:** 2026-09-20  

## Solution

```
class Solution {
public:
    int reverseDegree(string s) {
        int ans=0;

        for(int i=0; i<s.size();i++){
            int sum= 26-(s[i]-'a');
            int prod= sum*(i+1);
            ans= ans+prod;
        }
        return ans;
        
    }
};
```
