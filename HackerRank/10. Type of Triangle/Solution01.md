Using CASE statement:
## Method 1
```
select
Case
    WHEN a+b<=c OR b+c<=a OR a+c<=b THEN "Not A Triangle"
    WHEN a=b AND b=c THEN "Equilateral"
    WHEN a=b OR b=c OR a=c THEN "Isosceles"
    ELSE "Scalene"
END
From Triangles;
```

## Method 2

```
select
Case
    WHEN a+b<=c OR b+c<=a OR a+c<=b THEN "Not A Triangle"
    WHEN a=b AND b=c THEN "Equilateral"
    WHEN a=b OR b=c OR a=c THEN "Isosceles"
    ELSE "Scalene"
END AS triangleType
From Triangles;
```
