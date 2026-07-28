# confirmation rate/submissions/2084686419

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT s.user_id, IFNULL(ROUND(SUM(if(c.action='confirmed',1,0))/COUNT(c.action),2),0) AS confirmation_rate
FROM Signups s
LEFT JOIN Confirmations c
ON s.user_id=c.user_id
GROUP BY s.user_id;


```
