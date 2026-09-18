# first unique character in a string/submissions/2145406425

**Platform:** LeetCode  
**Date:** 2026-09-18  

## Solution

```
class Solution {
public:
    int firstUniqChar(string s) {
        unordered_map<int,int> mp;
        for(int i=0; i<s.size();i++){
            mp[s[i]]++;
        }
        for(int i=0; i<s.size();i++){
            if(mp[s[i]]==1) return i;
        }
        return -1;
        
    }
};
```
