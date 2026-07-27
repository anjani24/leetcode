# pandas

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT p.product_id,IFNULL( round(sum(p.price*s.units)/sum(s.units),2 ),0)AS average_price
FROM Prices p
LEFT JOIN UnitsSold s
On p.product_id=s.product_id AND s.purchase_date BETWEEN p.start_date AND p.end_date
GROUP BY p.product_id;



```
