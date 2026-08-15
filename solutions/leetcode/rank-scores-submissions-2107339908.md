# rank scores/submissions/2107339908

**Platform:** LeetCode  
**Date:** 2026-08-15  

## Solution

```
# Write your MySQL query statement below
select score, dense_rank() over(order by score desc) as 'rank'
from Scores

```
