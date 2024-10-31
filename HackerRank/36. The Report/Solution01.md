
```sql
SELECT
    CASE
        WHEN g.grade >= 8 THEN s.Name
        ELSE 'NULL'
    END AS Name,
    g.grade AS Grade,
    s.Marks AS Mark
FROM
    Students s
JOIN
    Grades g ON s.Marks BETWEEN g.min_mark AND g.max_mark
ORDER BY
    g.grade DESC,
    CASE
        WHEN g.grade >= 8 THEN s.Name
        ELSE NULL
    END,
    CASE
        WHEN g.grade < 8 THEN s.Marks
        ELSE NULL
    END;
```
