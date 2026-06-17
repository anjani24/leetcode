# gas station/submissions/2036281297

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
        int tank=0;
        int start=0;

        while(i< n){

            tank += gas[i]- cost[i];

            if( tank <0){
                start= i+1;
                tank=0;
            }
            i++;

        }

        return start;
        
    }
};
```
