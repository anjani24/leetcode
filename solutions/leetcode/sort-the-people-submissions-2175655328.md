# sort the people/submissions/2175655328

**Platform:** LeetCode  
**Date:** 2026-10-18  

## Solution

```
class Solution {
public:
    vector<string> sortPeople(vector<string>& names, vector<int>& heights) {
        int n= names.size();
        vector<string> ans;

        map<int,string, greater<int>>  mp;

        for(int i=0; i<n;i++){
            mp[heights[i]]=names[i];   
        }

        for(auto &a:mp){
            ans.push_back(a.second);
        }
        return ans;
        
    }
};
```
