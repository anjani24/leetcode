# asteroid collision/submissions/2105343956

**Platform:** LeetCode  
**Date:** 2026-08-13  

## Solution

```
class Solution {
public:
    vector<int> asteroidCollision(vector<int>& asteroids) {

        stack<int> st;
        vector<int> ans;
        int i=0;

        while(i<asteroids.size()){
            
            if((st.empty() && asteroids[i]<0) || (!st.empty() && st.top()<0 && asteroids[i]<0)){
                st.push(asteroids[i]);
                i++;
            }

            else if(asteroids[i]>0){
                st.push(asteroids[i]);
                i++;
            }
            else{ 
            while(!st.empty() && i<asteroids.size() && asteroids[i]<0 ){
                int p= abs(asteroids[i]);
                if(st.top()<p) {st.pop();}
                else if(st.top()==p){
                    st.pop();
                    i++;
                }
                else{i++;}
            }
            }

        }

        while(!st.empty()){
            ans.push_back(st.top());
            st.pop();
        }
        reverse(ans.begin(), ans.end());
        return ans;
    }
};
```
