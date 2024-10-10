Using LEFT & RIGHT functions:
> LEFT(city,1) : first letter of city  
> RIGHT(city,1) : last letter of city

```
select distinct city
from station
where left(city,1) NOT IN ('a','e','i','o','u','A','E','I','O','U')
AND right(city,1) NOT IN ('a','e','i','o','u','A','E','I','O','U');
```
