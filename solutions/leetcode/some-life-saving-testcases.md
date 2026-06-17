# Some life saving TestCases

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    bool isNStraightHand(vector<int>& hand, int groupSize) {
        if(hand.size() % groupSize != 0){
            return false;
        }
        sort(hand.begin(), hand.end());

        map<int, int> mp;

        for(int i=0; i<hand.size(); i++){

            mp[hand[i]]++;
        }

        for(auto &[key,val]: mp){

            if(val>0){
                for(int i=0; i< groupSize; i++){
                    if(val+i==0){
                        return false;
                    }
                }
            }
        }
        return true;
    }
};
```
