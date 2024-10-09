Using LEFT and RIGHT Function:
> Use DISTINCT, for unique city
> > Left(city,1) gets the first element from the city  
> > right(city,1) gets the last element from the city

```
select distinct city
from station
where left(city,1) NOT IN ('a','e','i','o','u')
or right(city,1) NOT IN ('a','e','i','o','u');
```
> <Mark>HackerRank handles the case sensitivity, but in general sql is case-sensitive so the correct approach would be: </Mark>

```
select distinct city
from station
where left(city,1) NOT IN ('a','e','i','o','u','A','E','I','O','U')
or right(city,1) NOT IN ('a','e','i','o','u','A','E','I','O','U');
```
