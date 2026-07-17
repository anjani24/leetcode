# add binary/submissions/2071339361

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
    string addBinary(string a, string b) {

        int i= a.size()-1;
        int j= b.size()-1;
        int carry=0;
        string ans;

        while(i>=0 && j>=0){
            int x= a[i]-'0';
            int y= b[j]-'0';
            int sum = x+y+carry;

            int a = sum%2;
            carry = sum/2;
            ans.insert(ans.begin(), a+'0');
            i--;
            j--;
        }
        
        while(i>=0){
            int x= a[i]-'0';
            int sum= x+carry;
            
            int a=sum%2;
            carry= sum/2;
            ans.insert(ans.begin(), a+'0');
            i--;
        }

        while(j>=0){
            int y= b[j]-'0';
            int sum= y+carry;
            
            int a=sum%2;
            carry= sum/2;
            ans.insert(ans.begin(), a+'0');
            j--;
        }

        if(carry==1){
            ans.insert(ans.begin(), 1+'0');
        }
        return ans;   
    }
};
```
