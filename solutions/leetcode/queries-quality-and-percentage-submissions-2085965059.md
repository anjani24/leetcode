# queries quality and percentage/submissions/2085965059

**Platform:** LeetCode  
**Date:** 2026-07-29  

## Solution

```
# Write your MySQL query statement below
SELECT query_name, ROUND(AVG(rating/position),2) AS quality, ROUND(SUM(if(rating<3,1,0))*100/COUNT(rating),2) AS poor_query_percentage
FROM Queries
GROUP BY query_name;


```
