# grumpy bookstore owner/submissions/2101542080

**Platform:** LeetCode  
**Date:** 2026-08-10  

## Solution

```
class Solution {
public:
    int maxSatisfied(vector<int>& customers, vector<int>& grumpy, int minutes) {

        int n=grumpy.size();
        int m=0;

        for(int i=0; i<n; i++){

            if(grumpy[i]==0){
                m+=customers[i];
            }
        }

        int l=0;
        int r=minutes-1;
        int ans=m;
        int a=0;
        for(int i=l; i<=r;i++){
            if(grumpy[i]==1){
                a+=customers[i];
            }
        }
        ans= max(a+m, ans);

        while(r<n){
            if(grumpy[l]==1){
                a-=customers[l];
            }
            l++;
            r++;
            if(r<n && grumpy[r]==1){
                a+=customers[r];
            }

            ans= max(a+m, ans);
        }
        return ans;  
    }
};
```
