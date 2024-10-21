### Only for learning Temporary Table Concept (For complex dataset)

```
CREATE TEMPORARY TABLE temp_max_earnings AS
SELECT months * salary AS total_earning
FROM employee;

SELECT MAX(total_earning) AS max_total_earning,
       COUNT(*) AS count_max_earning
FROM temp_max_earnings
WHERE total_earning = (SELECT MAX(total_earning) FROM temp_max_earnings);

DROP TABLE temp_max_earnings;
```
<hr/>

### Note!!!
<Mark>
This won't work on HackerRank --->>>
We don't have the necessary privileges to create temporary tables for security or performance reasons.
<Mark/>
  
<hr/>

### Explanation:
1. We first create a temporary table that stores the total earnings for each employee.
2. Then, we calculate the maximum total earnings and count how many employees have that maximum.
3. Finally, the temporary table is dropped.
