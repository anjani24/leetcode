# Why the input number cannot go to infinity (an explanation/proof that fits the context of a technical interview)

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
public:
    bool isHappy(int n) {

        unordered_set<int> mp;

        while(n>1){
            if(mp.find(n)!= mp.end()){
                return false;
            }
            mp.insert(n);
        
            int p=n;
            int sum =0;         
            while(p){
                int r=p%10;
                sum += (r*r);
                p=p/10;
            }
            n=sum;
            
        }
        return n==1;
        
    }
};
```
