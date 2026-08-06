# median of two sorted arrays/submissions/2096191509

**Platform:** LeetCode  
**Date:** 2026-08-06  

## Solution

```
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        double ans;
        int n1= nums1.size();
        int n2= nums2.size();
        int s= n1+n2;
        int l=0;
        int r=0;
        int i=0;

        vector<double> merged1(s/2+1);
        if(s%2==0){
            while(l+r<s/2+1){

                if(l<n1 &&(r>=n2 || nums1[l]<=nums2[r])){
                    merged1[i]=(double)nums1[l];
                    l++;
                }
                else if(r<n2){
                    merged1[i]=(double)nums2[r];
                    r++;
                }
                i++;
            }
            return (merged1[i-1]+merged1[i-2])/2;


        }
        vector<double> merged2(s/2+1);
        if(s%2==1){
            
            while(l+r<s/2+1){
                if(l<n1 && (r>=n2 || nums1[l]<=nums2[r])){
                    merged2[i]=(double)nums1[l];
                    l++;
                }
                else if(r<nums2.size()){
                    merged2[i]=(double)nums2[r];
                    r++;
                }
                i++;
            }
            return merged2.back();
        }
        return {};
    }
};
```
