# employee bonus/submissions/2084486667

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT e.name, b.bonus
FROM Employee e
LEFT JOIN Bonus b
ON e.empID= b.empID
WHERE b.bonus<1000 OR b.bonus IS NULL;
```
