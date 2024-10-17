<Mark>COUNT(*) : used to count the number of rows in a table.</Mark>

```

SELECT COUNT(*)
FROM CITY
WHERE POPULATION > 100000;

```
 
<hr />
Extra Information:  
If COUNT(ID) was used it would have counted the number of non-null id values that meet the condition specified, which in this case is having a population greater than 100,000.
<hr />

### It's usually better to use COUNT(*) unless you specifically need to count non-null values in a particular column.
