# not boring movies/submissions/2083489457

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT id, movie, description, rating
FROM Cinema
WHERE id%2!=0 AND description !='boring'
ORDER BY rating DESC;


```
