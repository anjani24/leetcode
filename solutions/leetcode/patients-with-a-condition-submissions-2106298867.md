# patients with a condition/submissions/2106298867

**Platform:** LeetCode  
**Date:** 2026-08-14  

## Solution

```
# Write your MySQL query statement below
-- select patient_id, patient_name, conditions
-- from Patients 
-- where conditions like '% DIAB1%' or conditions like 'DIAB1%'

SELECT patient_id, patient_name, conditions
FROM Patients
WHERE conditions REGEXP '\\bDIAB1';


```
