# time based key value store/submissions/2161798897

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
        auto &v=mp[key]; //yaha & is necessary
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

```
