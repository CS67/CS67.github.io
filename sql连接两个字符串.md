```sql
select 
concat(first_name,' ',last_name) 
as name
from patients;
```

等价于:

```sql
select 
first_name||last_name
as name
from patients;
```

[sql concat()](https://dev.mysql.com/doc/refman/8.4/en/sql-mode.html#sqlmode_pipes_as_concat)

*对待*[`||`](https://dev.mysql.com/doc/refman/8.4/en/logical-operators.html#operator_or)*作为字符串连接运算符（与*`CONCAT()`*相同），而不是作为*`OR`*的同义词。*