# shortest and lexicographically smallest beautiful string/submissions/2121436765

**Platform:** LeetCode  
**Date:** 2026-08-27  

## Solution

```
class Solution {
public:
    string shortestBeautifulSubstring(string s, int k) {

        if(s.size()<k) return "";

        int count=0;
        int r=0;
        int l=0;
        int sizee=s.size()+1;
        int min_start=-1;
        string ans=s;

        while(r<s.size()){

            if(s[r]=='1'){
                count++;
            }
            while(count==k){
                int curr_len=r-l+1;
                if(sizee> curr_len){
                    sizee=curr_len;
                    min_start=l;
                }
                else if(curr_len==sizee){
                    if(s.compare(l,curr_len, s, min_start, sizee)<0){
                        min_start=l;
                    }
                }
                if(s[l]=='1'){
                    count--;
                }
                l++;
            }
            r++;
        }
        if (min_start == -1) {
            return "";
        }
        
        return s.substr(min_start, sizee);
        
    }
};
```
