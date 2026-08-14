# product price at a given date/submissions/2106529209

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
-- # Write your MySQL query statement below
SELECT p1.product_id, p1.new_price as price
from Products p1
left join Products p2
on p1.product_id= p2.product_id and p2.change_date <='2019-08-16' and p1.change_date<p2.change_date
where p1.change_date<='2019-08-16' and p2.product_id is null

union 

select product_id, 10 as price
from Products
group by product_id
having min(change_date)> '2019-08-16'





```
