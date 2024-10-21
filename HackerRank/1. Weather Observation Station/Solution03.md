Using Regular Expressions:
>MYSQL supports regex!!!

```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[aeiou]';
```
