# game play analysis iv/submissions/2086535650

**Platform:** LeetCode  
**Date:** 2026-07-29  

## Solution

```
# Write your MySQL query statement below
SELECT ROUND(SUM(if(b.player_id,1,0))/COUNT(DISTINCT a.player_id),2) AS fraction
FROM Activity a
LEFT JOIN Activity b
ON a.player_id= b.player_id AND DATEDIFF(a.event_date,b.event_date)=1

```
