# max consecutive ones/submissions/2048054691

**Platform:** LeetCode  
**Date:** 2026-06-27  

## Solution

```
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {

        int count=0;
        int m=0;

        for(int i=0; i< nums.size(); i++){

            count=0;

            while(i< nums.size() && nums[i]==1){
                count = count+1 ;
                m= max(m, count);
                i++;
            }
        }

        return m;
        
    }
};
```
