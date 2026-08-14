# Hints

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
# Write your MySQL query statement below
select p.product_name, sum(o.unit)as unit
from Products p
JOIN Orders o
ON p.product_id= o.product_id
WHERE o.order_date BETWEEN '2020-02-01' AND '2020-02-29'
group by p.product_id
having unit>=100

```
