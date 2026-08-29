# longest consecutive sequence/solutions

**Platform:** LeetCode  
**Date:** 2026-08-29  

## Solution

```
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {

        unordered_map<int,int> mp;

        for(int i=0; i<nums.size(); i++){
            mp[nums[i]]++;
        }

        int i=0;
        int longest=0;

        while(i<nums.size()){
            int a=0;

            while(mp.find(nums[i]+a)!=mp.end()){
                a++;
            }

            longest= max(longest, a);
            i++;
        }

        return longest;
        
    }
};
```
