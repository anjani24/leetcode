# find smallest letter greater than target/description

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {

        int l=0;
        int r= letters.size()-1;

        if(target>=letters[r]) return letters[0];

        while(l<=r){
            int mid= l+(r-l)/2;
            if(target< letters[mid]) r= mid-1;
            else{
                l=mid+1;
            } 
        }
        return letters[l];
        
    }
};
```
