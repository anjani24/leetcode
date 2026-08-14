# find smallest letter greater than target/submissions/2106556184

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {

        int l=0;
        int r= letters.size()-1;

        if(target< letters[l]) return letters[0];
        if(target>letters[r]) return letters[0];

        while(l<=r){
            int mid= l+(r-l)/2;
            if(target< letters[mid]) r= mid-1;
            else if(target> letters[mid]) l= mid+1;
            else{
                if(mid+1<letters.size()) return letters[mid+1];
                else return letters[0];
            } 
        }
        return letters[l];
        
    }
};
```
