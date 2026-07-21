# maximize active section with trade i/submissions/2076272554

**Platform:** LeetCode  
**Date:** 2026-07-21  

## Solution

```
class Solution {
public:
    int maxActiveSectionsAfterTrade(string s) {
        int a=0;

        for(int i=0; i< s.size(); i++){
            if(s[i]=='1'){
                a++;
            }
        }

        // block of zeroes 

        vector<int> block;
        int c=0;
        for(int i=0; i< s.size(); i++){
            if(s[i]=='0'){
                c++;
            }
            else if(s[i]=='1'){
                block.push_back(c);
                c=0;
            }  
        }
        block.push_back(c);
        // remove zero-length blocks
        block.erase(remove(block.begin(), block.end(), 0), block.end());

        if(block.empty()) return a;

        int maxc=0;

        for(int i=0; i< block.size()-1; i++){
            int d= block[i];
            int b= block[i+1];

            maxc= max(maxc, d+b);
        }

        return a+ maxc;
        
    }
};
```
