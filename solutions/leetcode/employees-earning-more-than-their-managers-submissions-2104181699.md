# employees earning more than their managers/submissions/2104181699

**Platform:** LeetCode  
**Date:** 2026-08-12  

## Solution

```
# Write your MySQL query statement below
select e.name as Employee
from Employee e
join Employee m
on e.managerID=m.id
where e.salary>m.salary

```
