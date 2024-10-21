Using LEFT for String Manipulation

```sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city, 1) IN ('a', 'e','i','o', 'u');
```
