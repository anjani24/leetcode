# minimum number of pushes to type word ii/submissions/2087359245

**Platform:** LeetCode  
**Date:** 2026-07-30  

## Solution

```
class Solution {
public:
    int minimumPushes(string word) {
        int ans=0;

        // O(N+K^2) TC and O(K) space 

        // unordered_map<char,int> mp;

        // for(int i=0;  i< word.size(); i++){
        //     mp[word[i]]++;
        // }
        // int p=0;

        // while(!mp.empty()){
        //     auto maxit = max_element(mp.begin(), mp.end(), [](const auto&a, const auto&b) {return a.second<b.second;});
        //     ans = ans + ((p/8)+1)* maxit->second;
        //     mp.erase(maxit);
        //     p++;
        // }

        // Optimized to O(N)

        vector<int> freq(26,0);

        for(auto & p: word){
            freq[p-'a']++;
        }
        sort(freq.begin(), freq.end(), greater<int>());

        for(int i=0; i< freq.size(); i++){
            ans= ans+ freq[i]* ((i/8)+1);
        }
        return ans;   
    }
};
```
