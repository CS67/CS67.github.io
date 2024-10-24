这是一个查询 : 男性人数 和 女性人数, 要求显示在同一行

```sql
select sum(gender="M") as male ,sum(gender="F") as female from patients;
```

![image-20241024205454418](C:\Users\CS099\Documents\CS67.github.io\assets\image-20241024205454418.png)

关于case的语法如下:

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```



这个查询可以这样修改, 这里使用sum和count实现的效果一样. 返回1, sum是计算1的总和, count数1的次数.

```sql
select
sum(case when gender='M' then 1 end) male,
sum(case when gender='F' then 1 end) female
from patients
```

```sql
select
count(case when gender='M' then 1 end) male,
count(case when gender='F' then 1 end) female
from patients
```

