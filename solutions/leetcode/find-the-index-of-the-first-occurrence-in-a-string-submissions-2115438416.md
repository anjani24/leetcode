# find the index of the first occurrence in a string/submissions/2115438416

**Platform:** LeetCode  
**Date:** 2026-08-21  

## Solution

```
class Solution {
public:
    int strStr(string haystack, string needle) {
        
        int i=0;
        int j=0;
        int ans=0;

        while(i< needle.size() && j< haystack.size()){
            ans=j;
            while(i< needle.size() && j< haystack.size() && needle[i]==haystack[j]){
                i++;
                j++;

            }
            if(i==needle.size()) return ans;
            else{
                i=0;
            }
            j++;
        }
        return -1;
    }
};
```
