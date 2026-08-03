# triangle judgement/submissions/2092512058

**Platform:** LeetCode  
**Date:** 2026-08-03  

## Solution

```
# Write your MySQL query statement below
SELECT x,y,z, if(x+y>z and y+z>x and x+z>y,'Yes', 'No')AS triangle
FROM Triangle
```
