# managers with at least 5 direct reports/submissions/2084661859

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT name
FROM Employee
WHERE id IN (SELECT managerID
FROM Employee
GROUP BY managerID
HAVING COUNT(managerID)>=5)




```
