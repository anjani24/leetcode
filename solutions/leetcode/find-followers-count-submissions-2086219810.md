# find followers count/submissions/2086219810

**Platform:** LeetCode  
**Date:** 2026-07-29  

## Solution

```
# Write your MySQL query statement below
SELECT user_id, Count(follower_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id

```
