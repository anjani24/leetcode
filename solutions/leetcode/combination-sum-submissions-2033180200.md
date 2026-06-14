# combination sum/submissions/2033180200

**Platform:** LeetCode  
**Date:** 2026-06-14  

## Solution

```
class Solution {
public:
    vector<vector<int>> ans;
    void backtrack(vector<int> & candidates, vector<int> & curr, int target, int sum, int start){

        if(sum== target){
            ans.push_back(curr);
        }

        if(sum > target){
            return;
        }
          
        for(int i=start; i<candidates.size();i++){
            if (sum+ candidates[i]> target){
                break;
            }
            curr.push_back(candidates[i]);
            backtrack(candidates, curr, target, sum+ candidates[i], i);
            curr.pop_back();

        }
    }
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        sort(candidates.begin(), candidates.end());
        vector<int> curr;

        backtrack(candidates, curr, target, 0, 0);
        return ans;

    }
};
```
