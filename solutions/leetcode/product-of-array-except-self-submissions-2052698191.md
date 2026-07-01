# product of array except self/submissions/2052698191

**Platform:** LeetCode  
**Date:** 2026-07-01  

## Solution

```
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n= nums.size();
        vector<int> ans(n);
        vector<int> left(n);
        vector<int> right(n);
        int p=1;
        int q=1;
        left[0]=1;
        right[n-1]=1;
        for(int i=1; i<n; i++){
            p= nums[i-1]*p;
            left[i]= p; 
        }
        
        for(int i=n-2; i>=0; i--){
            q= nums[i+1] *q;
            right[i]= q;  
        }
        
        for(int i=0; i<n ;i++){
            ans[i]= left[i]* right[i];
        }
        return ans;
   
    }
};


/*
int n=nums.size();
vector<int>ans(n,1);
for(int i=1;i<n;i++)
{
ans[i]=ans[i-1]*nums[i-1];
}
for(int i=n-2;i>=0;i--)
{
ans[i]*=ans[i+1]*nums[i+1];
}
return ans;
*/


```
