# merge triplets to form target triplet/submissions/2036747556

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    bool mergeTriplets(vector<vector<int>>& triplets, vector<int>& target) {

        bool a=false, b=false, c=false;

        for(auto t: triplets){

            if(t[0]<= target[0] && t[1]<= target[1] && t[2]<= target[2]){
                if(t[0]==target[0]) a=true;
                if(t[1]==target[1]) b= true;
                if(t[2]== target[2]) c= true;
            }
        }

        if(a==true && b==true && c==true){
            return true;
        }
        return false;
    }
};
```
