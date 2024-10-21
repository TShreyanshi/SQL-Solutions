Using a Derived Table (Subquery in the FROM Clause)

```
SELECT MAX(total_earning) AS max_total_earning,
       COUNT(*) AS count_max_earning
FROM (SELECT months * salary AS total_earning FROM employee) AS derived
WHERE total_earning = (SELECT MAX(months * salary) FROM employee);
```

<hr/>

Explanation:
1. The inner query (SELECT months * salary AS total_earning) creates a derived table with the total earnings for each employee.
2. The outer query finds the maximum total earnings and counts how many employees have that maximum.
