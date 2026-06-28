# minimum window substring

**Platform:** LeetCode  
**Date:** 2026-06-28  

## Solution

```
class Solution {
public:
    string minWindow(string s, string t) {
        unordered_map<char,int>seen;
        unordered_map<char,int>req;
        int m=s.size();
        int n = t.size();
        int left=0;int right=0;
        int same=0;int ans=INT_MAX;
        int starting;
        int ending;
        for(int i=0;i<n;i++)
        {
            req[t[i]]++;
        }
        int need=req.size();
        while(right<m && left<=right)
        {
            seen[s[right]]++;
            if(req.count(s[right]) && req[s[right]]==seen[s[right]])same++;
    while(same==need){
        if(right-left+1<ans)
        {
            ans=right-left+1;
            starting=left;ending=right;
        }
        seen[s[left]]--;
        //tu karle agar aara samajh to mjse nahi hora
        if(req.count(s[left])&& seen[s[left]]<req[s[left]])same--;
        left++;
    }
    right++;
}
     if(ans==INT_MAX)return "";
     return s.substr(starting,ans);
     
     //string ans chiye
     //ni ara
    }//dekhlo ai se nahi hoga bina uske to mjse
    // hnnn dekh kr hi kra
    //bc v smol hai iska ans :Sob: samjh hi ni ata
};//oh aa gya to likh
//kuch to s.substr(i,j) se substring aa jata :sob:
```
