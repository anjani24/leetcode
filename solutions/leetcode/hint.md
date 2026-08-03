# 🔸 Hint :

**Platform:** LeetCode  
**Date:** 2026-08-03  

## Solution

```
# Write your MySQL query statement below
SELECT l1.num AS ConsecutiveNums
from Logs l1
join Logs l2
join Logs l3
ON l2.id= l1.id+1 and l3.id= l2.id+1
WHERE l1.num=l2.num and l2.num=l3.num



```
