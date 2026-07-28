# number of unique subjects taught by each teacher/submissions/2084499065

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT teacher_id, COUNT(DISTINCT subject_id) as cnt
FROM Teacher
GROUP BY teacher_id;


```
