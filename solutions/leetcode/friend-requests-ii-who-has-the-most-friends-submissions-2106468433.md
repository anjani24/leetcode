# friend requests ii who has the most friends/submissions/2106468433

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
with req as(
    select requester_id as id, count(requester_id) as rn
    from RequestAccepted
    group by requester_id

    union all

    select accepter_id as id, count(accepter_id) as rn
    from RequestAccepted
    group by accepter_id
)

select id, sum(rn) as num
from req
group by id
order by num desc
limit 1


```
