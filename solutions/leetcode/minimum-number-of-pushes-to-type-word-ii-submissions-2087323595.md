# minimum number of pushes to type word ii/submissions/2087323595

**Platform:** LeetCode  
**Date:** 2026-07-30  

## Solution

```
class Solution {
public:
    int minimumPushes(string word) {
        int ans=0;
        unordered_map<char,int> mp;

        for(int i=0;  i< word.size(); i++){
            mp[word[i]]++;
        }
        int p=0;

        while(!mp.empty()){
            auto maxit = max_element(mp.begin(), mp.end(), [](const auto&a, const auto&b) {return a.second<b.second;});
            ans = ans + ((p/8)+1)* maxit->second;
            mp.erase(maxit);
            p++;
        }
        return ans;   
    }
};
```
