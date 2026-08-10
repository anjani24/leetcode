# check if word is valid after substitutions/submissions/2101921787

**Platform:** LeetCode  
**Date:** 2026-08-10  

## Solution

```
class Solution {
public:
    bool isValid(string s) {
        string sub="abc";
        size_t pos;
        while((pos=s.find(sub))!=string::npos){
            s.erase(pos,3);
        }
        return (s=="");
        
    }
};
```
