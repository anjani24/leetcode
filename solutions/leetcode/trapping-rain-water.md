# trapping rain water

**Platform:** LeetCode  
**Date:** 2026-06-27  

## Solution

```
class Solution {
public:
    int trap(vector<int>& height) {
        int n=height.size();
        vector<int>leftmax(n);
        vector<int>rightmax(n);
        leftmax[0]=0;
        rightmax[n-1]=0;
        int ans=0;
        for(int i=1;i<n;i++)
        {
            leftmax[i]=max(leftmax[i-1],height[i-1]);
        }
        for(int i=n-2;i>=0;i--)
        {
            rightmax[i]=max(rightmax[i+1],height[i+1]);
        }
        for(int i=0;i<n;i++){
        if(height[i]<leftmax[i] && height[i]<rightmax[i])
        {
            ans+=min(leftmax[i],rightmax[i])-height[i];
        }
        }
        return ans;
    }
};
```
