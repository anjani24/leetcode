# time based key value store

**Platform:** LeetCode  
**Date:** 2026-10-04  

## Solution

```
class TimeMap {
public:
    unordered_map<string, vector<pair<string,int>>> mp;
    TimeMap() {
    }
    
    void set(string key, string value, int timestamp) {
        mp[key].push_back({value, timestamp});
    }
    
    string get(string key, int timestamp) {
        if(mp.count(key)==0)return "";
        
        //binary search
        auto v=mp[key];
        int n= v.size();
        int l=0;
        int h=n-1;
        string ans;
        while(l<=h){
            int mid= l+(h-l)/2;
            if(v[mid].second<=timestamp){
                l=mid+1;
                ans=v[mid].first;
            }
            else
            {
                h=mid-1;
            }
        }
        return ans;
        
        
    }
};

/**
 * Your TimeMap object will be instantiated and called as such:
 * TimeMap* obj = new TimeMap();
 * obj->set(key,value,timestamp);
 * string param_2 = obj->get(key,timestamp);
 */

 
 //tatvam space
// unordered_map<string,<pair<int,string>>>
// int n=mp.second.size()
// int l=0,h=n-1;
// int mid=l+(h-l)/2
// if(mid)
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 //anjanis space
 
// set- foo-1 , bar-1
//get- foo-1 fir foo-3 kaise ayaa???
//ky hui bubu set foo-bar-1 then get foo-1 give bar then get foo-3 give bar
 
 
```
