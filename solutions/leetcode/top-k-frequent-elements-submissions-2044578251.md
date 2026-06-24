# top k frequent elements/submissions/2044578251

**Platform:** LeetCode  
**Date:** 2026-06-24  

## Solution

```
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        vector<int> ans;
        unordered_map<int,int> mp;

        for(int i=0; i< nums.size(); i++){

            mp[nums[i]]++;
        }

        //convert map into vector

        //BUCKET SORT SOLUTION

        vector<vector<int>>bucket(nums.size()+1);

        for( auto a:mp){
            bucket[a.second].push_back(a.first);
        }

        for( int i=nums.size(); i>=0; i--){

            for(int x: bucket[i]){
                ans.push_back(x);

                if(ans.size()==k){
                    return ans;
                }
            }
        }
        return ans;
        
    }
};
```
