Using LEFT Function:
> Use DISTINCT, for unique city
> > Left(city,1) gets the first element from the city 

```
select DISTINCT city from station
where left(city,1) NOT IN ('a','e','i','o','u');
```
