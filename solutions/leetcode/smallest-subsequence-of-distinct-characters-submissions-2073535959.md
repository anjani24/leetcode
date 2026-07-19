# smallest subsequence of distinct characters/submissions/2073535959

**Platform:** LeetCode  
**Date:** 2026-07-19  

## Solution

```
class Solution {
public:
    string smallestSubsequence(string s) {

        unordered_map<char,int> mp;

        //last occurance 
        for(int i=0; i< s.size(); i++){
            mp[s[i]]=i;
        }

        stack<char> st;
        st.push(s[0]);
        
        //set to check if in stack
        unordered_set<char> instack;
        instack.insert(s[0]);

        for(int i=1; i< s.size(); i++){

            if(instack.count(s[i])){
                continue;
            }

            while( !st.empty() && st.top()> s[i] && mp[st.top()]>i){
                instack.erase(st.top());
                st.pop();
            }
            st.push(s[i]);
            instack.insert(s[i]);

        }

        string ans="";

        while(!st.empty()){
            ans.push_back(st.top());
            st.pop();
        }
        reverse(ans.begin(), ans.end());
        return ans;
    }
};
```
