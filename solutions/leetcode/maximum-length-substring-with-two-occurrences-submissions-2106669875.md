# maximum length substring with two occurrences/submissions/2106669875

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
class Solution {
public:
    int maximumLengthSubstring(string s) {
        unordered_map<char, int> mp;
        // for(char c: s){
        //     mp[c];
        // }
        // int p=0;
        // for(auto ch: mp){
        //     p++;
        // }


        int ans=0;
        int l=0;
        int r=0;

        while(r< s.size()){

            mp[s[r]]++;

            while(mp[s[r]]>2){
                mp[s[l]]--;
                l++;
            }
            
            ans= max(ans, r-l+1);
            r++;
        }


        return ans;

        
    }
};
```
