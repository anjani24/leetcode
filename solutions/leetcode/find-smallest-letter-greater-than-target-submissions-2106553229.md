# find smallest letter greater than target/submissions/2106553229

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {

        int l=0;
        int r= letters.size()-1;

        while(l<=r){
            int mid= l+(r-l)/2;
            if(target< letters[mid]) r= mid-1;
            else if(target> letters[mid]) l= mid+1;
            else return letters[mid+1];
        }
        return letters[0];
        
    }
};
```
