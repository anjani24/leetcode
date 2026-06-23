# multiply strings/submissions/2043439469

**Platform:** LeetCode  
**Date:** 2026-06-23  

## Solution

```
class Solution {
public:
    string multiply(string num1, string num2) {
        int n= num1.size();
        int m= num2.size();
        vector<int> ans(n+m,0);

        for(int i=n-1; i>=0; i--){
            for(int j=m-1; j>=0; j--){

                int digit1= num1[i]-'0';
                int digit2= num2[j]-'0';

                int p2= i+j+1;
                int p1= i+j;

                int d= digit1*digit2+ ans[p2];

                ans[p2]= d%10;
                ans[p1]+= d/10;
            }
        }

        int s=0;

        while(s<ans.size() && ans[s]==0){
            s++;
        }
        if(s==ans.size()){
            return "0";
        }

        string t;

        while(s < ans.size()){
            t.push_back(ans[s]+'0');
            s++;
        }

        return t;   
    }
};
```
