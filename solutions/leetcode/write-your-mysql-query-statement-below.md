# Write your MySQL query statement below

**Platform:** LeetCode  
**Date:** 2026-08-15  

## Solution

```
# Write your MySQL query statement below
select c.name as Customers
from Customers c
left join Orders o
on c.id=o.customerId
where o.customerId is null


```
