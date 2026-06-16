# valid parenthesis string/submissions/2035186969

**Platform:** LeetCode  
**Date:** 2026-06-16  

## Solution

```
class Solution {
public:
    // bool backtrack( string s, int idx, int balance){

    //     if (balance<0){
    //         return false;
    //     }

    //     if(idx== s.size()){
    //         if(balance==0){
    //             return true;
    //         }
    //         return false;
    //     }

    //     if(s[idx]=='('){
    //         return backtrack(s, idx+1, balance+1);
    //     }
    //     if(s[idx]==')'){
    //         return backtrack(s, idx+1, balance-1);
    //     }

    //     if(s[idx]=='*'){
    //         return(
    //             backtrack(s, idx+1, balance+1)||
    //             backtrack(s, idx+1, balance-1)||
    //             backtrack(s, idx+1, balance));
    //         }
    //     return false;
    // }
    bool checkValidString(string s) {

        int low=0;
        int high=0;

        for(int i=0; i<s.size(); i++){
            if(s[i]=='('){
                low++;
                high++;
            }
            else if(s[i]==')'){
                low--;
                high--;
            }
            else{
                low--;
                high++;
            }
            low= max(0, low);
            if(high<0){
                return false;
            }
        }
        if(low==0){return true;}
        return false;

        // if(backtrack(s, 0,0)){
        //     return true;
        // }
        // return false;
        
    }
};
```
