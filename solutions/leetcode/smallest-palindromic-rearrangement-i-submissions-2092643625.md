# smallest palindromic rearrangement i/submissions/2092643625

**Platform:** LeetCode  
**Date:** 2026-08-03  

## Solution

```
class Solution {
public:
    string smallestPalindrome(string s) {
        stack<char> st;
        int size= s.size();

        int n= floor(s.size()/2);

        string half= s.substr(0,n);
        sort(half.begin(), half.end());

        for(int i=0; i<n ;i++){
            s[i]=half[i];
            s[size-1-i]=half[i];
        }
        return s;
        
        
    }
};
```
