# minimum interval to include each query/submissions/2039048466

**Platform:** LeetCode  
**Date:** 2026-06-19  

## Solution

```
class Solution {
public:
    vector<int> minInterval(vector<vector<int>>& intervals, vector<int>& queries) {
        sort(intervals.begin(), intervals.end());

        vector<int> ans(queries.size());
        map<int,vector<int>> mp;
    
        for(int i=0; i< queries.size(); i++){
            mp[queries[i]].push_back(i);
        }

        // min heap for storing interval size, end time
        priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pq;

        int j=0;
        for(const auto & [q, idx]: mp){
            //add useful intervals
            while(j<intervals.size() && intervals[j][0]<= q){ 
                int intervalsize= intervals[j][1]- intervals[j][0]+1;
                pq.push({intervalsize, intervals[j][1]});
                j++;
            }

            //remove unnecessary intervals where end time< query value
            while(!pq.empty() && pq.top().second< q){
                pq.pop();
            }
            int result=-1;
            if(!pq.empty()){
                result= pq.top().first;
            }

            for(int index: idx){
                ans[index]=result;
            }
        }
        return ans;
    }
};
```
