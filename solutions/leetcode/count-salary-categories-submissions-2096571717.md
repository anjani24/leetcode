# count salary categories/submissions/2096571717

**Platform:** LeetCode  
**Date:** 2026-08-06  

## Solution

```
select 'Low Salary' as category , count(account_id) as accounts_count
from Accounts 
where income<20000
union
select 'Average Salary' as category, ifnull(count(account_id),0) as accounts_count
from Accounts
where income between 20000 and 50000
union
select 'High Salary' as category, ifnull(count(account_id),0) as accounts_count
from Accounts
where income>50000

```
