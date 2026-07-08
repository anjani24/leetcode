# third maximum number/submissions/2060884232

**Platform:** LeetCode  
**Date:** 2026-07-08  

## Solution

```
class Solution {
public:
    int thirdMax(vector<int>& nums) {
        set<int> top3;
        
        for (int num : nums) {
            top3.insert(num);
            if (top3.size() > 3) {
                top3.erase(top3.begin()); // Remove the smallest element
            }
        }

        return (top3.size() == 3) ? *top3.begin() : *top3.rbegin();
    }
};

```
