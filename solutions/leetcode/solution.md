# Solution

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
SELECT contest_id, ROUND(COUNT(contest_id)*100/(
    SELECT COUNT(user_id)
    FROM Users
),2) AS percentage
FROM Register
GROUP BY contest_id
ORDER BY percentage DESC, contest_id ASC;

```
