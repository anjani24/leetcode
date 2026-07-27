# find customer referee

**Platform:** LeetCode  
**Date:** 2026-07-27  

## Solution

```
# Write your MySQL query statement below
SELECT name
FROM Customer
WHERE referee_id != 2 OR referee_id IS NULL;

```
