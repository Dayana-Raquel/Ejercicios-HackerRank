# EjerciciosSQL-HackerRank
---
## SQL - INTERMEDIATE
---

### 5. Weather Observation Station 5:
```sql
select city, length(city) from station
order by length(city),city asc
limit 1;
select city, length(city) from station
order by length(city) desc
limit 1;
```

### 6. Binary Tree Nodes:
```sql
SELECT CASE
	WHEN P IS NULL THEN CONCAT(N, ' Root')
	WHEN N IN (SELECT DISTINCT P FROM BST) THEN CONCAT(N, ' Inner')
	ELSE CONCAT(N, ' Leaf')
	END
FROM BST
ORDER BY N ASC
```


