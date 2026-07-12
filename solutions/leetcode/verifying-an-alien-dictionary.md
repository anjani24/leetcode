# verifying an alien dictionary

**Platform:** LeetCode  
**Date:** 2026-07-12  

## Solution

```
class Solution {
public:
    bool isAlienSorted(vector<string>& words, string order) {
        int n=order.size();
        vector<int>ascii(26,0);
        for(int i=0;i<n;i++){
            ascii[order[i]-'a']=i;
        }
        for(auto i:words)
        {
            for(char c:i)
            {
                c=ascii[c-'a']+'a';
            }
        }
        return is_sorted(words.begin(),words.end());
    }
};
```
