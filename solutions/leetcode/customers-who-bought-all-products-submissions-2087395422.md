# customers who bought all products/submissions/2087395422

**Platform:** LeetCode  
**Date:** 2026-07-30  

## Solution

```
# Write your MySQL query statement below
SELECT customer_id
FROM Customer c
CROSS JOIN Product p
ON c.product_key= p.product_key
GROUP BY c.customer_id
HAVING COUNT(p.product_key)= (SELECT COUNT(DISTINCT product_key) FROM Product )

```
