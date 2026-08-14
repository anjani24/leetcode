# find users with valid e mails/submissions/2106275867

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
SELECT user_id, name, mail
FROM Users
WHERE mail REGEXP '^[A-Za-z][A-Za-z0-9_.-]*@leetcode\\.com$';

```
