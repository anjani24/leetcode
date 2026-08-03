# smallest palindromic rearrangement i

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

        // string half= s.substr(0,n);
        // sort(half.begin(), half.end());

        // for(int i=0; i<n ;i++){
        //     s[i]=half[i];
        //     s[size-1-i]=half[i];
        // }
        // return s;
        for(int i=0; i<n ;i++){
            if(!st.empty() && st.top()<s[i]){
                char p= st.top();
                st.pop();
                st.push(s[i]);
                st.push(p);

            }
            else{
                st.push(s[i]);
            }
        }
        int j=0;

        while(!st.empty()){
            s[j]=st.top();
            s[size-1-j]=st.top();
            st.pop();
            j++;
        }
        return s; 
    }
};
```
