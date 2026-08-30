# longest substring without repeating characters/description

**Platform:** LeetCode  
**Date:** 2026-08-30  

## Solution

```
class Solution {
public:
    int lengthOfLongestSubstring(string s) {

        
        // unordered_map<char,int> map;
        // int left=0;
        // int maxl=0;
        // for(int r=0; r<s.size(); r++){
        //     if(map.find(s[r])!=map.end()){
        //         left=max(left, map[s[r]]+1);
        //     }
        //     map[s[r]]=r;
        //     maxl= max( maxl, r-left+1);
        // }
        // return maxl;


        unordered_map<char, int> st;
        int l=0;
        int maxl=0;

        for(int r=0; r<s.size();r++){
            if(st.find(s[r])!=st.end()){
                l=max(l,st[s[r]]+1);
            }
            st[s[r]]=r;
            maxl= max(maxl, r-l+1);

        }

        return maxl;





        
    }
};
```
