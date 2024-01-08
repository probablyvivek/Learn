# 30 Days of Pandas

## Table of Contents

### Categories
  - [Data Filtering](#data-filtering)
  - [String Methods](#string-methods)


----

Date: 7th January 2024
## Data Filtering

[Big Countries](https://leetcode.com/problems/big-countries/description/?source=submission-noac) |
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

[Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/description/?envType=study-plan-v2&envId=30-days-of-pandas&lang=pythondata) |
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

[Customers Who Never Order](https://leetcode.com/problems/customers-who-never-order/description/?envType=study-plan-v2&envId=30-days-of-pandas&lang=pythondata) |
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
[Article Views I](https://leetcode.com/problems/article-views-i/description/?envType=study-plan-v2&envId=30-days-of-pandas&lang=pythondata) |
`Difficulty: Easy`

Solution:
```python
import pandas as pd

def article_views(views: pd.DataFrame) -> pd.DataFrame:
    # Filter rows where author_id and viewer_id are the same (authors viewing their own articles)
    authors_viewed_own_articles = views[views['author_id'] == views['viewer_id']]

    # Extract unique and sorted author_ids, then create a DataFrame
    unique_sorted_authors = pd.DataFrame({'id': sorted(authors_viewed_own_articles['author_id'].unique())})

    return unique_sorted_authors
```
[Back to top](#table-of-contents)

----

Date: 8th January 2024
## String Methods

[Invalid Tweets](https://leetcode.com/problems/invalid-tweets/description/?envType=study-plan-v2&envId=30-days-of-pandas&lang=pythondata) |
`Difficulty: Easy`

Solution:
```python
import pandas as pd

def invalid_tweets(tweets: pd.DataFrame) -> pd.DataFrame:
    invalid_tweets = tweets[tweets['content'].str.len() > 15]
    
    # Extracting just the tweet_id of invalid tweets
    invalid_tweet_ids = invalid_tweets[['tweet_id']]

    return(invalid_tweet_ids)
```