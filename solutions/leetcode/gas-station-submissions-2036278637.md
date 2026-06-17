# gas station/submissions/2036278637

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int canCompleteCircuit(vector<int>& gas, vector<int>& cost) {

        if (accumulate(gas.begin(), gas.end(),0)< accumulate(cost.begin(), cost.end(), 0)){
            return -1;
        }
    

        int n= gas.size();
        int i=0;

        while(i< n){


            if(gas[i] < cost[i]){
                i++;
            }
            else{
                return i;
            }
        }

        return i;
        
    }
};
```
