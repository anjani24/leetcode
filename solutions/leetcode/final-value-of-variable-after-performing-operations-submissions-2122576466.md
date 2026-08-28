# final value of variable after performing operations/submissions/2122576466

**Platform:** LeetCode  
**Date:** 2026-08-28  

## Solution

```
class Solution {
public:
    int finalValueAfterOperations(vector<string>& operations) {
        int x=0;

        for(int i=0; i< operations.size(); i++){
            if(operations[i]=="++X" || operations[i]=="X++") x+=1;
            if(operations[i]=="--X" || operations[i]=="X--") x-=1;
        }
        return x;
        
    }
};
```
