# contains duplicate ii/submissions/2067299758

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {

        unordered_set<int> st;

        for(int i=0; i<nums.size();i++){

            if(i>k){
                st.erase(nums[i-k-1]);
            }

            if(st.count(nums[i])){
                return true;
            }

            st.insert(nums[i]);
        }
        return false;
        
    }
};
```
