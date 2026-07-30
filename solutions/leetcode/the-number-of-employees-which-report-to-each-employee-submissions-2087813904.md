# the number of employees which report to each employee/submissions/2087813904

**Platform:** LeetCode  
**Date:** 2026-07-30  

## Solution

```
# Write your MySQL query statement below
SELECT e.employee_id, e.name, COUNT(r.reports_to)as reports_count, ROUND(AVG(r.age),0) AS average_age
FROM Employees e
JOIN Employees r
WHERE e.employee_id=r.reports_to
GROUP BY r.reports_to
HAVING COUNT(r.reports_to)>0
ORDER BY e.employee_id


```
