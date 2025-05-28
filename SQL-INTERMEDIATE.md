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

### 9.Top Competitors:
```sql
select h.hacker_id, h.name
from submissions s
inner join challenges c
on s.challenge_id = c.challenge_id
inner join difficulty d
on c.difficulty_level = d.difficulty_level 
inner join hackers h
on s.hacker_id = h.hacker_id
where s.score = d.score and c.difficulty_level = d.difficulty_level
group by h.hacker_id, h.name
having count(s.hacker_id) > 1
order by count(s.hacker_id) desc, s.hacker_id asc
```

### 10. Ollivander's Inventory:
```sql
select w.id, p.age, w.coins_needed, w.power from Wands as w join Wands_Property as p on (w.code = p.code) where p.is_evil = 0 and w.coins_needed = (select min(coins_needed) from Wands as w1 join Wands_Property as p1 on (w1.code = p1.code) where w1.power = w.power and p1.age = p.age) order by w.power desc, p.age desc
```


