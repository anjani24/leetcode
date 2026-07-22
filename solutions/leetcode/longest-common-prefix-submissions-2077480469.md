# longest common prefix/submissions/2077480469

**Platform:** LeetCode  
**Date:** 2026-07-22  

## Solution

```
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {

        string ans="";
        int c=0;

        string a= strs[0];

        for(auto str: strs){
            c=0;
            int i=0;
            while(i< str.size()){
                if(str[i]==a[i]){
                    c++;
                }
                else{
                    break;
                }
                i++;
            }
            a=str;
        }

        ans= strs[0].substr(0, c);
        return ans;
        
    }
};
```
