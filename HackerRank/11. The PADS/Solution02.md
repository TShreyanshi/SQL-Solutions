Using UNION ALL to add 2 SELECT query:

>When you use UNION ALL, the ORDER BY clause should only appear once at the end

```
-- First query
SELECT CONCAT(name, '(', LEFT(occupation, 1), ')') AS Result
FROM OCCUPATIONS

UNION ALL

-- Second query
SELECT CONCAT('There are a total of ', COUNT(occupation), ' ', LOWER(occupation), 's.') AS Result
FROM OCCUPATIONS
GROUP BY occupation

ORDER BY Result;
```
