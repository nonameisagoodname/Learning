![
](<截屏2026-11-16 17.49.45.png>)


判断字符数的方法 CHAR_LENGTH(content) > 15

# JOIN 
是 SQL 中非常重要的知识点，它的作用是：把两张或多张表根据某个共同字段连接起来
记住：LEFT JOIN = 左表全部保留，右表有匹配就连接，没有匹配就显示 NULL。
记住：RIGHT JOIN = 右表全部保留。
FULL OUTER JOIN 左表所有数据保留。右表所有数据保留。匹配上的连接起来。 没有匹配的另一侧显示 NULL。
![alt text](<images/截屏2026-11-16 18.17.53.png>)

JOIN 就是INNER JOIN


CROSS JOIN（交叉联结）是 SQL 中的一种连接方式。它的作用是：将第一张表的每一行，分别与第二张表的每一行组合起来。也叫做笛卡尔积（Cartesian Product）。

DATEDIFF()
作用：计算两个日期之间相差多少天。date1 - date2，结果单位是天数。
TIMESTAMPDIFF()
作用：计算两个日期或时间之间相差多少时间，可以指定单位。

分区间问题”的本质是多条件判断，要想到用SQL里的case表达式知识来实现】

分区间问题”的本质是多条件判断，要想到用SQL里的case表达式知识来实现

![alt text](<images/截屏2026-11-16 18.48.45.png>)


```sql
SELECT id, name, city
FROM (
    SELECT *,
           ROW_NUMBER() OVER (
               PARTITION BY name, city
               ORDER BY id DESC
           ) AS rn
    FROM users
) AS t
WHERE rn = 1;
```
![alt text](<images/截屏2026-11-16 19.03.18.png>)

COUNT 就是数行数，或者数某一列中非 NULL 的值有多少个。

