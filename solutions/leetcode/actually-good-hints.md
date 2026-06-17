# 😇 Actually Good Hints

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    vector<int> partitionLabels(string s) {

        vector<int> ans;
        map<char, int> mp;


        for(int i=0; i< s.size(); i++){
            mp[s[i]]=i;
        }

        int j=0;

        while(j<s.size()){
            int r= mp[s[j]];
            int count=0;

            for(int k=j; k<r; k++){
                count++;

                // r= max(r, mp[s[k]]);
                if (mp[s[k]]> r){
                    r=mp[s[k]];
                }
            }

            ans.push_back(count+1);
            j= r+1;
        }
        return ans;
        
    }
};
```
