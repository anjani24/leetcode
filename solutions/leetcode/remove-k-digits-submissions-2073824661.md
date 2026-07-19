# remove k digits/submissions/2073824661

**Platform:** LeetCode  
**Date:** 2026-07-19  

## Solution

```
class Solution {
public:
    string removeKdigits(string num, int k) {

        if(num.size()==k){
            return "0";
        }

        stack<char> st;
        st.push(num[0]);

        for(int i=1; i< num.size(); i++){
            while(!st.empty() && k>0 && st.top()> num[i]){
                st.pop();
                k--;
            }
            st.push(num[i]);                                      
        }

        while(k>0){ st.pop();
            k--;
        }

        string ans ="";

        while(!st.empty()){
            ans.push_back(st.top());
            st.pop();
        }
        reverse(ans.begin(), ans.end());

        int idx=0;
        while(idx< ans.size() && ans[idx]=='0'){
            idx++;
        }
        ans= ans.substr(idx);

        return (ans.empty())? "0": ans;
        
    }
};

```
