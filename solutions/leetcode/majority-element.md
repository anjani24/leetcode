# majority element

**Platform:** LeetCode  
**Date:** 2026-07-02  

## Solution

```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        unordered_map<int, int> mp;
        int n= nums.size();
        
        for(int i=0; i< nums.size(); i++){
            mp[nums[i]]++;
        }

        for( auto a: mp){
            if(a.second> n/2){
                return a.first;
            }
        }
        return -1;  
    }
};


/*



hlo
idhr hi likh lo

okok
nai maarugi
kaise krte ye???????????????

yesss okiiii
 
 oki but O(1) space oki
 

//map 
//okay itne enter mat maar neeche chla jaata
//q hi nhi padha itne tu soch humpe time nahi jldiiiiiiii sppeeeedddd
































*/
// what are you doing dont make enters for space vo to hota rhega
```
