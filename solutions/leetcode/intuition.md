# Intuition

**Platform:** LeetCode  
**Date:** 2026-08-06  

## Solution

```
# Write your MySQL query statement below
SELECT q1.person_name
FROM Queue q1
JOIN Queue q2
on q1.turn>=q2.turn
Group by q1.turn

having sum(q2.weight)<=1000
order by q1.turn DESC
limit 1



```
