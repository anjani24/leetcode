# combination sum ii/submissions/2033203337

**Platform:** LeetCode  
**Date:** 2026-06-14  

## Solution

```
class Solution {
public:
    vector<vector<int>> ans;
    void backtrack(vector<int> & candidates, int target, vector<int> & curr, int sum, int start){
        if(sum== target){
            ans.push_back(curr);
            return;
        }

        for(int i=start; i<candidates.size(); i++){

            if(sum+ candidates[i]>target){
                break;
            }
            if(i>start && candidates[i]== candidates[i-1]){
                continue;
            }
            curr.push_back(candidates[i]);
            backtrack(candidates, target, curr, sum + candidates[i], i+1 );
            curr.pop_back();
        }
    }
    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        sort(candidates.begin(), candidates.end());
        vector<int> curr;
        backtrack(candidates, target, curr, 0, 0);
        return ans;
        
    }
};
```
