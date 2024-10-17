QUERY 1:
```
SELECT SUM(POPULATION)/COUNT(*)
FROM CITY 
WHERE DISTRICT = 'California';
```
<hr />
QUERY 2:

```
SELECT SUM(POPULATION)/COUNT(POPULATION)
FROM CITY 
WHERE DISTRICT = 'California';
```

<hr />

### NOTE !!
If you have a null value and you don't want to include it in your average then use:  
Also QUERY 2 corresponds to AVG function query
