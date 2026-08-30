# longest substring without repeating characters/submissions/2124723574

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


        unordered_set<int> st;
        int n= s.size();
        int l=0;
        int maxl=0;
        int r=0;
        
        while(r<n && l<=r){

            maxl= max(maxl, r-l);

            if(st.find(s[r])!=st.end()){
                st.erase(s[l]);
                l++;
            }
            else{
                st.insert(s[r]);
                r++;
            }
            
        }
        return maxl;  
    }
};
```
