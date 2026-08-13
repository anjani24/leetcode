# delete duplicate emails/submissions/2105246697

**Platform:** LeetCode  
**Date:** 2026-08-13  

## Solution

```
-- delete from Person
-- where id not in(select id from(select min(id)as id from Person group by email)t);

delete p1
from Person p1
join Person p2
on p1.email= p2.email
where p1.id>p2.id
```
