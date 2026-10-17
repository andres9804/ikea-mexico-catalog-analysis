## Data Profiling and Catalog Audit Analysis
From the **structural analysis** we can confirm that the dataset does not have missing values. Null values in critical columns like product_measurements or product_description can affect the customer experience or make it harder for the customers to find the right product for them.

The number of total unique IDs and product IDs match the total number of rows, which means there is a unique ID for every product and there are not repeated products.

For the **individual columns analysis** the following transformations might be considered:
- `"product_id"` data type "int64" into "str".
- `"main_category"` change data type "str" into "category". The columns consists of only 23 different values.
- `"badge"` change data type from "str" into "category".
- `"sale_tag"` change data type from "str" into "category".
- `"product_rating"` and `"product_rating_count"` change data types to float32. Transforming these columns into float values will enable calculations on such columns.
- Drop `"currency"` column. Working on a subset for a specific country makes a specific column for currency values unnecessary, dropping the column depends on the designated use of the dataset after the process (i.e. joining this subset to another country's dataset may require to stablish a currency value for each).
- Drop `"discount"` column since it contains no relevant values for this subset.

**Business logic dataset's analysis**
Dataset was checked for negative or equal to zero prices, missing or mismatched measurements and consistency between rating scores and number of ratings.
No inconsistencies were found. Having an inconsistency in any of the above mentioned might result in a negative experience for the customer and it also might cause problems for the customer to find the right products.