# immediate food delivery ii/submissions/2084758723

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT ROUND(SUM(if(d.order_date=d.customer_pref_delivery_date,1,0))/COUNT(d.order_date)*100,2) AS immediate_percentage
FROM Delivery d
LEFT JOIN Delivery p
ON d.customer_id=p.customer_id AND d.order_date > p.order_date
WHERE p.order_date IS NULL

```
