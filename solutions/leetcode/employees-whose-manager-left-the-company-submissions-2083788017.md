# employees whose manager left the company/submissions/2083788017

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT employee_id
FROM Employees
WHERE salary<30000 AND manager_id NOT IN(SELECT employee_id FROM Employees);

```
