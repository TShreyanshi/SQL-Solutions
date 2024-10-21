```
SELECT MAX(months * salary) AS max_total_earning,
       COUNT(*) AS count_max_earning
FROM employee
WHERE (months * salary) = (SELECT MAX(months * salary) FROM employee);
```
<hr/>

### Note !!!

```
SELECT MAX(months * salary) AS max_total_earning,
       COUNT(*) AS count_max_earning
FROM employee
WHERE (months * salary) = max_total_earning;
```

This won't work correctly because <MARK>WHERE CLAUSE</MARK> excutes before <MARK>SELECT CLAUSE</MARK> i.e. we cannot refer to an alias in the WHERE clause of the same query.

<hr/>

### More Insights

SQL Query Execution Order:  
1. FROM: The source data is gathered.
2. WHERE: Filters rows before any aggregate functions are applied.
3. GROUP BY: Groups rows if needed.
4. HAVING: Filters groups after aggregation (used with aggregate functions).
5. SELECT: Finally, the selected columns and any aliases are processed.
6. ORDER BY: The result set is sorted.
