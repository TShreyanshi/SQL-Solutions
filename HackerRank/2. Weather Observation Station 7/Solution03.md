Using **SUBSTRING**:

```
SELECT DISTINCT city
FROM station
WHERE SUBSTRING(city, LENGTH(city), 1) IN ('a', 'e', 'i', 'o', 'u');
```
