```sql
WITH challenge_counts AS (
    SELECT hacker_id, COUNT(*) AS clgCreatedPerHacker
    FROM challenges
    GROUP BY hacker_id
),
max_count AS (
    SELECT MAX(clgCreatedPerHacker) AS maxChallengeCount
    FROM challenge_counts
),
unique_counts AS (
    SELECT clgCreatedPerHacker
    FROM challenge_counts
    GROUP BY clgCreatedPerHacker
    HAVING COUNT(*) = 1
)
SELECT h.hacker_id, h.name, cc.clgCreatedPerHacker AS totalChallenges
FROM hackers h
JOIN challenge_counts cc ON h.hacker_id = cc.hacker_id
WHERE cc.clgCreatedPerHacker = (SELECT maxChallengeCount FROM max_count)
   OR cc.clgCreatedPerHacker IN (SELECT clgCreatedPerHacker FROM unique_counts)
ORDER BY cc.clgCreatedPerHacker DESC, h.hacker_id ASC;
```
