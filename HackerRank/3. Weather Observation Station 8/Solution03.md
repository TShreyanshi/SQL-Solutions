Using LIKE funtion with NOT;

```
select DISTINCT city from station
where city NOT LIKE 'a%'
AND city NOT LIKE 'e%'
AND city NOT LIKE 'i%'
AND city NOT LIKE 'o%'
AND city NOT LIKE 'u%';
```

>This question Automatically deals with case sensitivity, but in general sql is case-sensitive so the correct approach would be:

```
SELECT DISTINCT city 
FROM station 
WHERE city NOT LIKE 'A%' 
  AND city NOT LIKE 'E%' 
  AND city NOT LIKE 'I%' 
  AND city NOT LIKE 'O%' 
  AND city NOT LIKE 'U%' 
  AND city NOT LIKE 'a%' 
  AND city NOT LIKE 'e%' 
  AND city NOT LIKE 'i%' 
  AND city NOT LIKE 'o%' 
  AND city NOT LIKE 'u%';
```
