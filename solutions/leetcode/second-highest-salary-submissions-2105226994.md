# second highest salary/submissions/2105226994

**Platform:** LeetCode  
**Date:** 2026-08-13  

## Solution

```
# Write your MySQL query statement below
select(
select salary 
from(select salary , dense_rank() over(order by salary desc) as rnk from Employee) t
where rnk=2 
limit 1) as SecondHighestSalary
```
