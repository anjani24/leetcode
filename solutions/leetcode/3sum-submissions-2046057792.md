# 3sum/submissions/2046057792

**Platform:** LeetCode  
**Date:** 2026-06-25  

## Solution

```
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        vector<vector<int>> ans;
        int n= nums.size();
        
        int p=0;
        int l= p+1;
        int r= n-1;

        sort(nums.begin(), nums.end());

        while(p<n-2){

            if(p>0 && nums[p]==nums[p-1]){
                p++;
                continue;
            }
            l=p+1;
            r= n-1;

            while(l<r){
                if(nums[p]+ nums[l]+ nums[r]==0){
                ans.push_back({nums[p], nums[l], nums[r]});

                l++;
                r--;

                while(l<r && nums[l]==nums[l-1]){
                    l++;
                }
                while(l<r && nums[r]== nums[r+1]){
                    r--;
                }

                }

                else if(nums[p]+ nums[l]+ nums[r]>0){
                r--;                
                }
                else{
                l++;
                }
            }
            p++;   
        }

        return ans;
        
    }
};
```
