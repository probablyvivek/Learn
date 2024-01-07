# 30 Days of Pandas

## Table of Contents

### Categories
  - [Data Filtering](#data-filtering)


----

Date: 7th January 2024
## Data Filtering

[Big Countries](https://leetcode.com/problems/big-countries/description/?source=submission-noac)
`Difficulty: Easy`

Solution:
```python
import pandas as pd

def big_countries(world: pd.DataFrame) -> pd.DataFrame:
    # Filtering for countries with either a large area or a large population
    large_area = world['area'] >= 3000000
    large_population = world['population'] >= 25000000
    big_countries_df = world[large_area | large_population]

    # Returning a DataFrame with specified columns
    return big_countries_df[['name', 'population', 'area']].reset_index(drop=True)
```

[Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/description/?envType=study-plan-v2&envId=30-days-of-pandas&lang=pythondata)
`Difficulty: Easy`

Solution:
```python
import pandas as pd

def find_products(products: pd.DataFrame) -> pd.DataFrame:
    # Filtering for products that are both low in fats and recyclable
    is_low_fats = products['low_fats'] == 'Y'
    is_recyclable = products['recyclable'] == 'Y'
    recyclable_df = products[is_low_fats & is_recyclable]

    # Returning a DataFrame with only the 'product_id' column
    return recyclable_df[['product_id']].reset_index(drop=True)
```

[Customers Who Never Order](https://leetcode.com/problems/customers-who-never-order/description/?envType=study-plan-v2&envId=30-days-of-pandas&lang=pythondata)
`Difficulty: Easy`

Solution:
```python
import pandas as pd

def find_customers(customers: pd.DataFrame, orders: pd.DataFrame) -> pd.DataFrame:
    # Merge customers with orders, using a left join to keep all customers
    merged_df = pd.merge(customers, orders, left_on='id', right_on='customerId', how='left')

    no_order_customers = merged_df[merged_df['customerId'].isna()]

    # Create a DataFrame with just the 'name' column, renaming it to 'Customers'
    result_df = no_order_customers[['name']].rename(columns={'name': 'Customers'}).reset_index(drop=True)

    return result_df
```



[Back to top](#table-of-contents)

----