# SQL

## MySQL

SQL query to find all numbers that appear at least three times consecutively.(LeetCode)

```SQL

with cte 
as
(select id, num, lead(num,1) over(order by id) as leadone, lead(num,2) over(order by id) as leadtwo
 from logs
)

select distinct num as ConsecutiveNums
    from cte 
where num = leadone and num = leadtwo and leadone = leadtwo


```
