# Top 50 Leet Code SQL Problems

## Table of Contents
  - [Category: Select](#category-select)


## Category: Select

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
SELECT DISTINCT author_id AS id
FROM Views
WHERE author_id = viewer_id;
```




[Back to top](#table-of-contents)

