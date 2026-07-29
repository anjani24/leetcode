# Solution

**Platform:** LeetCode  
**Date:** 2026-07-29  

## Solution

```
# Write your MySQL query statement below
SELECT m.machine_id, ROUND(AVG(p.timestamp-m.timestamp),3)AS processing_time
FROM Activity m
JOIN Activity p
ON m.machine_id=p.machine_id AND m.process_id=p.process_id AND m.activity_type='start' AND p.activity_type='end'
GROUP BY m.machine_id


```
