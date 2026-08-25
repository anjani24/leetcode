# smallest missing multiple of k/submissions/2119278119

**Platform:** LeetCode  
**Date:** 2026-08-25  

## Solution

```
class Solution {
public:
    int missingMultiple(vector<int>& nums, int k) {

        unordered_map<int,int> mp;

        for(auto a: nums){
            mp[a]++;
        }
        int n=k;

        while(n){
            if(mp.find(n)==mp.end()){
                return n;
            }
            n=n+k;
        }
        return n;
        
    }
};
```
