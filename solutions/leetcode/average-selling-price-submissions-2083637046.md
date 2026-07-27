# average selling price/submissions/2083637046

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT p.product_id, round(sum(p.price*s.units)/sum(s.units),2 )AS average_price
FROM Prices p
JOIN UnitsSold s
On p.product_id=s.product_id
WHERE s.purchase_date BETWEEN p.start_date AND p.end_date
GROUP BY p.product_id;



```
