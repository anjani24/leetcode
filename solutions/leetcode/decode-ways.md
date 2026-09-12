# decode ways

**Platform:** LeetCode  
**Date:** 2026-09-12  

## Solution

```
class Solution {
public:
    int solver(string &s,int i, vector<int> &dp){
        if(i==s.size()){
            return 1;
        }
        if(s[i]=='0'){
            return 0;
        }
        
        int ways=0;

        if(dp[i]!=-1){
            return dp[i];
        }
        //one digit
        ways+=solver(s, i+1, dp);

        //2 digits
        if(i+1<s.size()){
            int num= stoi(s.substr(i,2));
            if(num>=10 && num<=26){
                ways+= solver(s,i+2, dp);
            }
        }

        return dp[i]=ways;

    }
    int numDecodings(string s) {

        vector<int> dp(s.size(),-1);
        int count= solver(s,0, dp);
        return count;
    }
};
```
