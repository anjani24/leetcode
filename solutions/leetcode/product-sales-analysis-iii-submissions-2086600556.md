# product sales analysis iii/submissions/2086600556

**Platform:** LeetCode  
**Date:** 2026-07-29  

## Solution

```
# Write your MySQL query statement below
SELECT product_id, MIN(year) as first_year, quantity, price
FROM Sales
GROUP BY product_id


```
