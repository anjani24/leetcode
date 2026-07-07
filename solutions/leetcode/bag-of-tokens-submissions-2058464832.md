# bag of tokens/submissions/2058464832

**Platform:** LeetCode  
**Date:** 2026-07-07  

## Solution

```
class Solution {
public:
    int bagOfTokensScore(vector<int>& tokens, int power) {

                sort(tokens.begin(), tokens.end());
        int l = 0, r = tokens.size() - 1;
        int score = 0, max_score = 0;
        
        while (l <= r) {
            if (power >= tokens[l]) {
                power -= tokens[l];
                score++;
                max_score = max(max_score, score);
                l++;
            } else if (score > 0) {
                power += tokens[r];
                score--;
                r--;
            } else {
                break;
            }
        }
        return max_score;

    
    }
};


```
