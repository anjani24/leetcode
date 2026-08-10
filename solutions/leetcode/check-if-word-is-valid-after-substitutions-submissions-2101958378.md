# check if word is valid after substitutions/submissions/2101958378

**Platform:** LeetCode  
**Date:** 2026-08-10  

## Solution

```
class Solution {
public:
    bool isValid(string s) {
    //     string sub="abc";
    //     int pos;
    //     while((pos=s.find(sub))!=string::npos){
    //         s.erase(pos,3);
    //     }
    //     return (s=="");
    // }

    // o(n)
    stack<char> st;

    for(int i=0; i<s.size(); i++){
        if(s[i]=='c'){
            if(st.empty() || st.top()!='b'){
                return false;
            }
            else{
                st.pop();
            }
            if(st.empty() || st.top()!='a'){
                return false;
            }
            else st.pop();

        }
        else{
            st.push(s[i]);
        }
    }

    return st.empty();
    }
};
```
