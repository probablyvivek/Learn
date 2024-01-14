# Top 50 Leet Code SQL Problems

## Table of Contents

#### Categories
  - [Select](#category-select)
  - [Basic Joins](#basic-joins)

---
Date: 6th January 2024
## Select

 [Recyclable and Low Fat Products]( https://leetcode.com/problems/recyclable-and-low-fat-products/?envType=study-plan-v2&envId=top-sql-50) |
 `Difficulty: Easy`

Solution:
```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';
```

[Find Customer Referee](https://leetcode.com/problems/find-customer-referee/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT name FROM Customer
WHERE referee_id <> 2 OR referee_id IS NULL;
```

[Big Countries](https://leetcode.com/problems/big-countries/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT name, population, area
FROM World
WHERE area >= 3000000 OR population >= 25000000;
```

[Article View](https://leetcode.com/problems/article-views-i/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT DISTINCT author_id as id
FROM Views
WHERE author_id = viewer_id
ORDER BY author_id ASC;
```

[Invalid Tweets](https://leetcode.com/problems/invalid-tweets/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT tweet_id
FROM Tweets
WHERE CHAR_LENGTH(content)>15;
```
Note: `CHAR_LENGTH()` is used instead of `LENGTH()` because `LENGTH()` counts the number of bytes in a string, whereas `CHAR_LENGTH()` counts the number of characters in a string.

I first used `LENGHT()` but the execution time was too long (1196 ms) but when I used `CHAR_LENGTH()` the execution time was reduced to 919 ms.

[CHAR_LENGTH() Function Explanation](https://www.w3schools.com/sql/func_mysql_char_length.asp#:~:text=The%20CHAR_LENGTH()%20function%20return,to%20the%20CHARACTER_LENGTH()%20function)

[Back to top](#table-of-contents)

----

Date: 7th January 2024
## Basic Joins

[Replace Employee ID With The Unique Identifier](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT u.unique_id, e.name
FROM Employees e
LEFT JOIN EmployeeUNI u ON e.id = u.id
```

[Product Sales Analysis I](https://leetcode.com/problems/product-sales-analysis-i/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT p.product_name, s.year, s.price
FROM Sales s
JOIN Product p ON p.product_id = s.product_id
```

[Customer Who Visited but Did Not Make Any Transactions](https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/description/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT v.customer_id, count(*) as count_no_trans
FROM Visits v
LEFT JOIN Transactions t ON v.visit_id = t.visit_id
WHERE t.visit_id IS NULL
GROUP BY v.customer_id;
```

[Rising TemperatureRising Temperature](https://leetcode.com/problems/rising-temperature/description/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT w1.id
FROM Weather w1
JOIN Weather w2 
ON DATEDIFF(w1.recordDate, w2.recordDate) = 1
WHERE w1.Temperature > w2.Temperature;
```

```I don't how this was tagged as an easy problem. I lost my mind trying to solve this problem. All the time I was thinking the solution has to be straightforward as it was tagged as easy. I knew SELF JOIN was to be used but the DATE_DIFF function was something I had to google and learn. ```

[Back to top](#table-of-contents)

----

Date: 9th January 2024

[Average Time of Process per Machine](https://leetcode.com/problems/average-time-of-process-per-machine/description/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
select a1.machine_id, round(avg(a2.timestamp-a1.timestamp), 3) as processing_time 
from Activity a1
join Activity a2 
on a1.machine_id=a2.machine_id and a1.process_id=a2.process_id
and a1.activity_type='start' and a2.activity_type='end'
group by a1.machine_id
```

Date: 10th January 2024

[Employee Bonus](https://leetcode.com/problems/employee-bonus/description/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT Employee.name, Bonus.bonus
FROM Employee
LEFT JOIN Bonus ON Employee.empId = Bonus.empId
WHERE Bonus.bonus < 1000 OR Bonus.bonus IS NULL;
```

Date: 11th January 2024
[Students and Examinations](https://leetcode.com/problems/students-and-examinations/description/?envType=study-plan-v2&envId=top-sql-50) |
`Difficulty: Easy`

Solution:
```sql
SELECT
    Students.student_id,
    Students.student_name,
    Subjects.subject_name,
    COUNT(Examinations.subject_name) AS attended_exams
FROM Students 
JOIN Subjects
LEFT JOIN Examinations
ON Students.student_id = Examinations.student_id
AND Subjects.subject_name = Examinations.subject_name
GROUP BY Students.student_id, Subjects.subject_name
ORDER BY student_id ASC, subject_name ASC
```

Date: 12th January 2024
...


