# find users with valid e mails/submissions/2106278236

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
SELECT user_id, name, mail
FROM Users
WHERE REGEXP_LIKE(mail, '^[A-Za-z][A-Za-z0-9_.-]*@leetcode\\.com$', 'c');


```
