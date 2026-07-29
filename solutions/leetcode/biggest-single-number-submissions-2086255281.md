# biggest single number/submissions/2086255281

**Platform:** LeetCode  
**Date:** 2026-07-29  

## Solution

```
# Write your MySQL query statement below
SELECT (
    SELECT num
    FROM MyNumbers
    GROUP BY num
    HAVING COUNT(num)=1
    ORDER BY num desc
    LIMIT 1
) AS num


```
