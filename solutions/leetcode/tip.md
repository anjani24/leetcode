# 🔸Tip :

**Platform:** LeetCode  
**Date:** 2026-08-03  

## Solution

```
# Write your MySQL query statement below
SELECT employee_id, department_id
FROM Employee
WHERE primary_flag='Y' or employee_id in (select employee_id from employee group by employee_id having count(employee_id)=1)


```
