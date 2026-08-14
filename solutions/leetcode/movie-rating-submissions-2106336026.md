# movie rating/submissions/2106336026

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
# Write your MySQL query statement below
with topuser as(
    select u.name as results
    from MovieRating m
    join Users u
    on m.user_id=u.user_id
    Group by m.user_id
    order by COUNT(m.user_id) desc, u.name asc
    limit 1
),
topmovie as(
    select mv.title as results
    from MovieRating m
    join Movies mv
    ON m.movie_id= mv.movie_id
    where m.created_at between '2020-02-01' and '2020-02-29'
    group by m.movie_id
    order by avg(m.rating) desc, mv.title asc
    limit 1
)

select results from topuser
union all
select results from topmovie
```
