# Top 50 Leet Code SQL Problems

## Table of Contents

### Categories
  - [Select](#category-select)
  - [Basic Joins](#basic-joins)

---
Date: 6th January 2024
## Select

 [Recyclable and Low Fat Products]( https://leetcode.com/problems/recyclable-and-low-fat-products/?envType=study-plan-v2&envId=top-sql-50)
 `Difficulty: Easy`

Solution:
```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';
```

[Find Customer Referee](https://leetcode.com/problems/find-customer-referee/?envType=study-plan-v2&envId=top-sql-50) 
`Difficulty: Easy`

Solution:
```sql
SELECT name FROM Customer
WHERE referee_id <> 2 OR referee_id IS NULL;
```

[Big Countries](https://leetcode.com/problems/big-countries/?envType=study-plan-v2&envId=top-sql-50)
`Difficulty: Easy`

Solution:
```sql
SELECT name, population, area
FROM World
WHERE area >= 3000000 OR population >= 25000000;
```

[Article View](https://leetcode.com/problems/article-views-i/?envType=study-plan-v2&envId=top-sql-50)
`Difficulty: Easy`

Solution:
```sql
SELECT DISTINCT author_id as id
FROM Views
WHERE author_id = viewer_id
ORDER BY author_id ASC;
```

[Invalid Tweets](https://leetcode.com/problems/invalid-tweets/?envType=study-plan-v2&envId=top-sql-50)
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

[Replace Employee ID With The Unique Identifier](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/?envType=study-plan-v2&envId=top-sql-50)
`Difficulty: Easy`

Solution:
```sql
SELECT u.unique_id, e.name
FROM Employees e
LEFT JOIN EmployeeUNI u ON e.id = u.id
```

[Product Sales Analysis I](https://leetcode.com/problems/product-sales-analysis-i/?envType=study-plan-v2&envId=top-sql-50)
`Difficulty: Easy`

Solution:
```sql


