# minimum window substring/submissions/2049245168

**Platform:** LeetCode  
**Date:** 2026-06-28  

## Solution

```
class Solution {
public:
    string minWindow(string s, string t) {
        int m= s.size();
        int n= t.size();
        
        if(m<n){
            return "";
        }

        unordered_map< char, int> mp;

        for(auto a : t){
            mp[a]++;
        }
        int need= n;
        int i = 0, best_start = 0, best_len = INT_MAX;

        for (int j = 0; j < m; j++) {

            if(mp[s[j]]>0) need--;
            mp[s[j]]--;
        
            while (need == 0) {

                if(j-i+1< best_len){
                    best_len= min(best_len,j-i+1);
                    best_start=i;
                }

                mp[s[i]]++;
                if(mp[s[i]]>0) need++;
                i++;
            }
        }
    
        return best_len == INT_MAX ? "" : s.substr(best_start, best_len);

    }
};
//

```
