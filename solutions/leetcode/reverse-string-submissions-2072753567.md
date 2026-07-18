# reverse string/submissions/2072753567

**Platform:** LeetCode  
**Date:** 2026-07-18  

## Solution

```
class Solution {
public:
    void reverseString(vector<char>& s) {

        int i=0;
        int j= s.size()-1;
        
        while(i<j){
            swap(s[i], s[j]);
            i++;
            j--;
        }
    }
};
```
