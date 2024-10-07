Using Regular Expressions:
>MYSQL supports regex!!!

```
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[aeiou]';
```
