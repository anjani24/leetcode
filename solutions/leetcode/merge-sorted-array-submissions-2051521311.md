# merge sorted array/submissions/2051521311

**Platform:** LeetCode  
**Date:** 2026-06-30  

## Solution

```
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {

        int p=m-1;
        int q=n-1;
        int i=m+n-1;

        if(m==0){
            nums1= nums2;
        }
        
        if(!nums1.empty() && !nums2.empty()){

        while(p>=0 && q>=0){

            if(nums1[p]>= nums2[q]){
                nums1[i]=nums1[p];
                p--;
            }

            else{
                nums1[i]= nums2[q];
                q--;
            }
            i--;
        }
        while(q>=0){
            nums1[i]= nums2[q];
            q--;
            i--;
        }

        }
    }
};
```
