# restaurant growth/submissions/2106427021

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
# Write your MySQL query statement below
with dailyTotal as(
    select visited_on, SUM(amount) as daily_total
    from Customer
    group by visited_on
),
moving as( 
select visited_on ,sum(daily_total) over(order by visited_on rows between 6 preceding and current row) as amount, round(avg(daily_total) over(order by visited_on ROWS Between 6 PRECEDING and current row),2)as average_amount, row_number() over(order by visited_on) as day
from dailyTotal
)

select visited_on, amount, average_amount
from moving
where day>=7


```
