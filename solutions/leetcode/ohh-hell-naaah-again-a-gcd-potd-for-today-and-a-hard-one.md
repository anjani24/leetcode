# ohh hell naaah again a gcd potd for today and a hard one

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
    vector<int> gcdValues(vector<int>& nums, vector<long long>& queries) {
        // Find the upper bound limit for our buckets
        int maxNum = *max_element(nums.begin(), nums.end());
        
        // Step 1: Record how many times each number appears in the input
        vector<long long> frequencies(maxNum + 1, 0);
        for (int num : nums) {
            frequencies[num]++;
        }
        
        // Step 2: Use Inclusion-Exclusion to find exact GCD pair counts.
        // We iterate backwards so that larger multiples are computed first.
        vector<long long> exactGcdPairs(maxNum + 1, 0);
        
        for (int i = maxNum; i >= 1; i--) {
            // Count how many numbers in the array are multiples of 'i'
            long long multipleCount = 0;
            for (int j = i; j <= maxNum; j += i) {
                multipleCount += frequencies[j];
            }
            
            // Total pairs that share 'i' as a common divisor
            long long totalPairs = (multipleCount * (multipleCount - 1)) / 2;
            
            // Inclusion-Exclusion: Subtract pairs whose actual GCD is a strict multiple of 'i'
            for (int j = 2 * i; j <= maxNum; j += i) {
                totalPairs -= exactGcdPairs[j];
            }
            
            exactGcdPairs[i] = totalPairs;
        }
        
        // Step 3: Build a running total (prefix sum) of the pair counts.
        // This conceptually blocks out the index ranges for each GCD value.
        vector<long long> prefixSums(maxNum + 1, 0);
        for (int i = 1; i <= maxNum; i++) {
            prefixSums[i] = prefixSums[i - 1] + exactGcdPairs[i];
        }
        
        // Step 4: Answer the queries efficiently using binary search
        vector<int> ans;
        ans.reserve(queries.size());
        
        for (long long q : queries) {
            // upper_bound finds the first position where the running total exceeds the query index
            auto it = upper_bound(prefixSums.begin(), prefixSums.end(), q);
            int actualGcdValue = distance(prefixSums.begin(), it);
            ans.push_back(actualGcdValue);
        }
        
        return ans;
    }
};

```
