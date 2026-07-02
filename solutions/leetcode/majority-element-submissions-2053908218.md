# majority element/submissions/2053908218

**Platform:** LeetCode  
**Date:** 2026-07-02  

## Solution

```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int ans=0;
        int count=0;
        int n=nums.size();
        for(int i=0;i<n;i++)
        {
            if(ans==nums[i])count++;
            else if(count==0){
                ans= nums[i];
                count++;
            }
            else if (ans!=nums[i]){
                count--;
            }
        } 
        return ans;
    }
};
```
