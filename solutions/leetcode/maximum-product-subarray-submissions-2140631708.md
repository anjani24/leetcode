# maximum product subarray/submissions/2140631708

**Platform:** LeetCode  
**Date:** 2026-09-13  

## Solution

```
class Solution {
public:
    int maxProduct(vector<int>& nums) {

        int n=nums.size();
        int ans=0;

        vector<int> maximum(n+1);
        vector<int> minimum(n+1);

        maximum[0]=nums[0];
        minimum[0]=nums[0];

        for(int i=1; i<n;i++){


            maximum[i]= max({nums[i], maximum[i-1]*nums[i], minimum[i-1]*nums[i]});
            minimum[i]= min({nums[i], minimum[i-1]*nums[i], maximum[i-1]*nums[i]});
            ans= max(ans, maximum[i]);

        }
        
        return maximum[n];



        
    }
};
```
