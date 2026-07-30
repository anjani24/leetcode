# customers who bought all products/submissions/2087399264

**Platform:** LeetCode  
**Date:** 2026-07-30  

## Solution

```
# Write your MySQL query statement below
SELECT customer_id
FROM Customer 
GROUP BY customer_id
HAVING COUNT(DISTINCT product_key)= (SELECT COUNT(DISTINCT product_key) FROM Product )

```
