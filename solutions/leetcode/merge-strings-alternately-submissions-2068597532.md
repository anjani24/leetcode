# merge strings alternately/submissions/2068597532

**Platform:** LeetCode  
**Date:** 2026-07-15  

## Solution

```
class Solution {
public:
    string mergeAlternately(string word1, string word2) {
        int i=0;
        int j=0;
        int m= word1.size();
        int n= word2.size();
        int a=0;
        int size= m+n;
        string ans(m+n, 'a');

        while(i<m && j<n && a< size){
            ans[a]= word1[i];
            ans[a+1]=word2[j];
            a +=2;
            i++;
            j++;
        }
        while(i<m){
            ans[a]= word1[i];
            i++;
            a++;
        }
        while(j<n){
            ans[a]=word2[j];
            j++;
            a++;
        }
        return ans;
        
    }
};
```
