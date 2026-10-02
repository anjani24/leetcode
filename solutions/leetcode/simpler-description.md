# Simpler Description

**Platform:** LeetCode  
**Date:** 2026-10-02  

## Solution

```
class Solution {
public:
    int numRabbits(vector<int>& a) {
        unordered_map<int,int> mp;
        int ans=0;
        for(int i=0;i<a.size();i++){
            int sz=a[i]+1;
            if(mp[a[i]]%sz==0)ans+=sz;
            mp[a[i]]++;
        }
        return ans;
    }
};

```
