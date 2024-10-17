#### Using Common Table Expression (CTE) i.e. WITH
>  It helps structure SQL queries by allowing to define temporary result sets that can be referenced in the main query.

1. Calculate the correct average monthly salary :
   AVG(salary)
2. Calculate the miscalculated average by removing all zeros from salaries :
   AVG(CAST(REPLACE(salary, '0', '') AS UNSIGNED))
   > CAST AS UNSIGNED : convert back to Integer
3. Calculate the absolute difference and round up to the nearest integer:
   CEIL(correct_avg-miscalculated_avg)

<hr />

```
WITH CorrectAvg AS (
    SELECT AVG(salary) AS correct_avg
    FROM EMPLOYEES
),
MiscalculatedAvg AS (
    SELECT AVG(CAST(REPLACE(salary, '0', '') AS UNSIGNED)) AS miscalculated_avg
    FROM EMPLOYEES
)
SELECT CEIL(correct_avg-miscalculated_avg) AS error_amount
FROM CorrectAvg , MiscalculatedAvg ;
```
