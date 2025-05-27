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

### 7. New Companies:
```sql
select c.company_code, 
    c.founder, 
    count(distinct e.lead_manager_code), 
    count(distinct e.senior_manager_code), 
    count(distinct e.manager_code), 
    count(distinct e.employee_code)
from company c
    inner join employee e on e.company_code = c.company_code
group by c.company_code,c.founder
order by c.company_code;
```

### 8. Weather Observation Station 20:

```sql
select round(s.lat_n, 4) from station as s where ( (select count(lat_n) from station where s.lat_n >= lat_n) - (select count(lat_n) % 2 from station) = (select count(lat_n) from station where s.lat_n < lat_n) )
```

