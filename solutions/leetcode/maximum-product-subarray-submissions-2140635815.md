# maximum product subarray/submissions/2140635815

**Platform:** LeetCode  
**Date:** 2026-09-13  

## Solution

```
class Solution {
public:
    int maxProduct(vector<int>& nums) {

        int n=nums.size();
        if(n==0) return 0;
        
        vector<int> maximum(n);
        vector<int> minimum(n);

        int ans=nums[0];

        maximum[0]=nums[0];
        minimum[0]=nums[0];

        for(int i=1; i<n;i++){


            maximum[i]= max({nums[i], maximum[i-1]*nums[i], minimum[i-1]*nums[i]});
            minimum[i]= min({nums[i], minimum[i-1]*nums[i], maximum[i-1]*nums[i]});
            ans= max(ans, maximum[i]);

        }
        
        return ans;
    }
};
```
