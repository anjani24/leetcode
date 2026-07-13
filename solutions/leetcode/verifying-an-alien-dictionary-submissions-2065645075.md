# verifying an alien dictionary/submissions/2065645075

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
class Solution {
public:
    bool isAlienSorted(vector<string>& words, string order) {
        int n=order.size();
        vector<int>ascii(n,0);
        for(int i=0;i<n;i++){
            ascii[order[i]-'a']=i;
        }
        for(auto& i:words)
        {
            for(char& c:i)
            {
                c=ascii[c-'a'];
            }
        }
        return is_sorted(words.begin(),words.end());
    }
};
//["ubg","kwh"]
//"qcipyamwvdjtesbghlorufnkzx"



```
