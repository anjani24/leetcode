# HINT

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT project_id, AVG(experience_years) AS average_years
FROM Project p
LEFT JOIN Employee e
On p.employee_id= e.employee_id
Group by p.project_id;


```
