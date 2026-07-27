# not boring movies/submissions/2083487674

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT id, movie, description, rating
FROM Cinema
WHERE id%2!=0 AND description !='boring'
ORDER BY id DESC;


```
