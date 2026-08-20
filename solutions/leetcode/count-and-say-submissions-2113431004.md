# count and say/submissions/2113431004

**Platform:** LeetCode  
**Date:** 2026-08-20  

## Solution

```
class Solution {
public:
    string rle(string s){

        string p="";
        int l=0;
        int r=0;
        int count=0;
        
        while(r< s.size()){

            while(r<s.size()&& s[r]==s[l]){
                count++;
                r++;
            }

            p+= to_string(count)+s[l];
            l=r;
        }
        return p;

    }
    string countAndSay(int n) {

        string ans="1";      
        while(n>1){
            ans= rle(ans);
            n--;
        }
        return ans;
        
    }
};
```
