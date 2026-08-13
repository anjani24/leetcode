# delete duplicate emails/submissions/2105235669

**Platform:** LeetCode  
**Date:** 2026-08-13  

## Solution

```
# Write your MySQL query statement below
select id, email
from(select * , row_number() over(partition by email order by id) as rnk from Person ) t
where rnk=1
limit 1

```
