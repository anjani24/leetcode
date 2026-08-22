# longest subsequence with non zero bitwise xor/submissions/2115712526

**Platform:** LeetCode  
**Date:** 2026-08-22  

## Solution

```
class Solution {
public:
    int longestSubsequence(vector<int>& nums) {

        int l=0;
        int r=1;
        int longest=0;
        int x=nums[l];

        while(r<nums.size() && l<nums.size()){

            x=x^nums[r];

            if(x>0){
                longest= max(longest, r-l+1);
                r++;
            }
            else{
                x=x^nums[l];
                l=l+1;
                r++;
            }
        }

        return longest;
        
    }
};
```
