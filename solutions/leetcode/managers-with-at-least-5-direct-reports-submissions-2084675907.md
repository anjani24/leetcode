# managers with at least 5 direct reports/submissions/2084675907

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT e.name
FROM Employee e
JOIN Employee m
ON e.id= m.managerID
GROUP BY m.managerID
HAVING COUNT(m.managerID)>=5;




```
