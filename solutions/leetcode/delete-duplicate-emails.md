# delete duplicate emails

**Platform:** LeetCode  
**Date:** 2026-08-13  

## Solution

```
delete from Person
where id not in(select id from(select min(id)as id from Person group by email)t);
```
