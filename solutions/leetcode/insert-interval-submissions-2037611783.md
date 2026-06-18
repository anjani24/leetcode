# insert interval/submissions/2037611783

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {

        vector<vector<int>> ans;
        bool inserted= false;

        for(auto i: intervals){
            if(newInterval[1]< i[0]){
                if(!inserted){
                    ans.push_back(newInterval);
                    inserted= true;
                }
                ans.push_back(i);  
            }
            else if(newInterval[0]> i[1]){
                ans.push_back(i);
            }

            else{
                newInterval[0] = min(i[0], newInterval[0]); 
                newInterval[1] = max ( i[1], newInterval[1]);
            }
        }
        if(!inserted){
            ans.push_back(newInterval);
        }
        return ans;   
    }
};
```
