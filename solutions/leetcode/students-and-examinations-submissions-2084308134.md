# students and examinations/submissions/2084308134

**Platform:** LeetCode  
**Date:** 2026-07-28  

## Solution

```
# Write your MySQL query statement below
SELECT s.student_id, s.student_name, sub.subject_name, IFNULL(COUNT(e.student_id),0) AS attended_exams
FROM Students s
CROSS JOIN Subjects sub
LEFT JOIN Examinations e
ON e.subject_name=sub.subject_name AND s.student_id=e.student_id
GROUP BY s.student_id, sub.subject_name
ORDER BY s.student_id, sub.subject_name;
```
