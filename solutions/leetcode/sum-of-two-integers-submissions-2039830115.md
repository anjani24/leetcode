# sum of two integers/submissions/2039830115

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int getSum(int a, int b) {

        while(b!=0){
            int sum= a^b;
            int carry= (a&b)<<1;
            a=sum ;
            b= carry;

        }
        return a;   
    }
};
```
