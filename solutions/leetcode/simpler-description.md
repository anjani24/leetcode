# Simpler Description

**Platform:** LeetCode  
**Date:** 2026-10-02  

## Solution

```
class Solution {
public:
    int numRabbits(vector<int>& answers) {
        
        unordered_map<int,int> mp;
        
        for(int i=0;i<answers.size();i++){
            mp[answers[i]]++;
        }
        int ans=0;
        
        for(auto a : mp){
            if(a.second>a.first){
                int n=(a.first+1)/a.second;
                ans += n*(a.first+1);  
            }
            else{
                ans+= a.first+1;
            }
            
        }
        return ans; 
    }
};
```
