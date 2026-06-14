# Try  Permutations ||

**Platform:** LeetCode  
**Date:** 2026-06-14  

## Solution

```
class Solution {
public:
    vector<vector<int>> result;
    void backtrack(vector<int>& nums, vector<bool> & used, vector<int>& curr){

        if(curr.size()==nums.size()){
            result.push_back(curr);
            return;
        }

        for(int i=0; i<nums.size(); i++){
            if(used[i]){
                continue;
            }
            used[i]=true;
            curr.push_back(nums[i]);
            backtrack(nums, used, curr);

            used[i]= false;
            curr.pop_back();
        }
    }
    vector<vector<int>> permute(vector<int>& nums) {
        vector<int> curr;
        vector<bool> used(nums.size(),false);
        backtrack(nums, used, curr);
        return result;
           
    }
};
```
