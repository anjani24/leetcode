# unique 3 digit even numbers/submissions/2138189883

**Platform:** LeetCode  
**Date:** 2026-09-11  

## Solution

```
class Solution {
public:
    int totalNumbers(vector<int>& digits) {

        if(digits.size()<3) return 0;

        vector<int> v(10,0);

        for(int i=0; i< digits.size(); i++){
            v[digits[i]]++;
        }

        int ans=0;

        //units
        for(int units=0; units <=8; units +=2){
            if(v[units]==0) continue;
            v[units]--;

            //hundreds
            for(int h=1; h<=9; h++){

                if(v[h]==0) continue;
                v[h]--;

                //tens
                for(int t=0; t<=9;t++){
                    if(v[t]==0) continue;
                    ans++;
                }

                v[h]++;
            }
            v[units]++;
        }
        return ans;
    }
};
```
