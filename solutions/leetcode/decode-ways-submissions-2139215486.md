# decode ways/submissions/2139215486

**Platform:** LeetCode  
**Date:** 2026-09-12  

## Solution

```
class Solution {
public:
    // int solver(string &s,int i, vector<int> &dp){
    //     if(i==s.size()){
    //         return 1;
    //     }
    //     if(s[i]=='0'){
    //         return 0;
    //     }
        
    //     int ways=0;

    //     if(dp[i]!=-1){
    //         return dp[i];
    //     }
    //     //one digit
    //     ways+=solver(s, i+1, dp);

    //     //2 digits
    //     if(i+1<s.size()){
    //         int num= stoi(s.substr(i,2));
    //         if(num>=10 && num<=26){
    //             ways+= solver(s,i+2, dp);
    //         }
    //     }

    //     return dp[i]=ways;
    // }
    int numDecodings(string s) {
        
        int n=s.size();
        vector<int> dp(n+1,0);

        dp[0]=1;
        if(s[0]!='0') dp[1]=1;

        for(int i=2; i<=n;i++){

            //one digit
            if(s[i-1]!='0'){
                dp[i]+=dp[i-1];
            }

            //two digits
            int num= (s[i-2]-'0')*10+(s[i-1]-'0');
            if(num>=10 && num<=26){
                dp[i] +=dp[i-2];
            }
        }
        return dp[n];
    }
};
```
