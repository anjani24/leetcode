# lexicographically smallest permutation greater than target/submissions/2121646436

**Platform:** LeetCode  
**Date:** 2026-08-27  

## Solution

```
class Solution {
public:

    string lexGreaterPermutation(string s, string target) {
        int n= s.size();
        vector<int> freq(26,0);
        for(int i=0; i<n ;i++){
            freq[s[i]-'a']++;
            freq[target[i]-'a']--;
        }

        for(int i=n-1; i>=0; i--){
            int cur= target[i]-'a';
            
            freq[cur]++;
            bool ok= true;

            // Can the prefix [0...i-1] still be matched?
            for (int x : freq) {
                if (x < 0) {
                    ok = false;
                    break;
                }
            }
            if (!ok) continue;

            // Find the smallest character > target[i]
            for (int nxt = cur + 1; nxt < 26; nxt++) {

                if (freq[nxt] == 0) continue;

                freq[nxt]--;

                string ans = target.substr(0, i);
                ans.push_back(char('a' + nxt));

                for (int c = 0; c < 26; c++) {
                    ans.append(freq[c], char('a' + c));
                }

                return ans;
            }
        }
        return "";
    
    }
};
```
