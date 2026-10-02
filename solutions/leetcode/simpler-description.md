# Simpler Description

**Platform:** LeetCode  
**Date:** 2026-10-02  

## Solution

```
class Solution {
public:
    int numRabbits(vector<int>& answers) {
        unordered_set<int>st;
        for(int i:answers)
        {
            st.insert(i+1);
        }
        int ans=0;
        for(int i:st)
        {
            ans+=i;
        }
        return ans;
    }
};




//
```
