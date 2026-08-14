# department top three salaries/submissions/2106492193

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
# Write your MySQL query statement below


select d.name as Department, e.name as Employee, e.salary as Salary
from (select *, DENSE_RANK() OVER(partition by departmentId order by salary desc) as rnk
from Employee) e
join Department d
on e.departmentId= d.id
where rnk<=3
order by Department, salary desc;




```
