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
    big_countries_df = world[(world['area'] >= 3000000) | (world['population'] >= 25000000)]
    return big_countries_df[['name', 'population', 'area']] 
```
