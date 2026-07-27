# replace employee id with the unique identifier

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT d.unique_id, e.name
FROM Employees e
LEFT JOIN EmployeeUNI d
ON e.id= d.id;

```
