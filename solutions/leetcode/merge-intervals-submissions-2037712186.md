# merge intervals/submissions/2037712186

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {

        vector<vector<int>> ans;
        int n= intervals.size();

        sort(intervals.begin(), intervals.end(), [](vector<int> & a, vector<int> & b){
            return a[0]<b[0];
        });

        vector<int> merger= intervals[0];

        for(int i=1; i<n; i++){

            if(merger[1]>= intervals[i][0]){
                merger[0] = min(merger[0],intervals[i-1][0]);
                merger[1]= max(merger[1],intervals[i][1]);
            }

            else{
                ans.push_back(merger);
                merger= intervals[i];
            }
        }
        ans.push_back(merger);

        return ans;    
    }
};
```
