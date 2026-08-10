# grumpy bookstore owner/submissions/2101534950

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
        int r=minutes;
        int ans=m;
        
        while(r<=n){
            int a=0;
            for(int i=l; i<r;i++){
                if(grumpy[i]==1){
                    a+=customers[i];
                }
            }
            ans= max(a+m, ans);
            l++;
            r++;
        }
        return ans;  
    }
};
```
