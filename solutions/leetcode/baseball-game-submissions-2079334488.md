# baseball game/submissions/2079334488

**Platform:** LeetCode  
**Date:** 2026-07-25  

## Solution

```
class Solution {
public:
    int calPoints(vector<string>& operations) {
        stack<int> st;

        for(auto p: operations){

            if(p=="+"){
                int a= st.top();
                st.pop();
                int b= st.top();
                st.push(a);

                st.push(a+b);
            }

            else if(p=="C"){
                st.pop();
            }
            else if(p=="D"){
                st.push(2* st.top());
            }
            else{
                int r= stoi(p);
                st.push(r);
            }
        }
        int sum=0;

        while(!st.empty()){
            sum += st.top();
            st.pop();
        }
        return sum;
        
    }
};
```
