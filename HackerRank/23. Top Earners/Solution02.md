Using HAVING clause:

```
SELECT months * salary AS total_earning,
       COUNT(*) AS count_max_earning
FROM employee
GROUP BY total_earning
HAVING total_earning = (SELECT MAX(months * salary) FROM employee);
```

<hr/>

Explanation:
1. GROUP BY total_earning: Group the rows by months * salary (i.e., total earnings).
2. HAVING: Filter the groups to only include the one with the maximum total earnings.
3. The HAVING clause is used here because it allows the use of aggregate functions after the GROUP BY.
