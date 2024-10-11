Using SUBSTRING function:

>SUBSTRING(Name, -3) extracts the last three characters of each name.  
>The ORDER BY clause first sorts by these last three characters and then by ID in ascending order if there are ties.

```
SELECT Name
FROM STUDENTS
WHERE Marks > 75
ORDER BY SUBSTRING(Name, -3), ID ASC;
```

