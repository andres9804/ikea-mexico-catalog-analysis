The following transformations will be applied to the respective columns based on previous analysis:
- `"main_category"` from "str" to "category" data type.
- `"badge"` from "str" to "category" data type.
- `"sale_tag"` from "str" to "category" data type.
- `"product_id"` from "int64" to "str" data type.
- `"product_rating"` from "str" to "float32" data type.
- `"product_rating_count"` from "str" to "float32" data type.
- `"discount"` from "str" to "float32" data type.
- `"currency"` column dropped.

To enable the previous transformations the following changes will be applied:
- "none" values transformed to NaN values for the following columns: `"product_rating", "product_rating_count", "discount"`
  
Transforming "none" string values to NaN values can reduce the dataset's size, enabling better calculations in numerical columns for analysis in BI tools.

#### Feature Selection
Being a subset for a single country and having a single currency, the `"currency"` column does not contribute any relevancy for the dataset. Removing it might reduce memory consumption and makes the dataset cleaner to process in Power BI.

The `"discount"` column for this subset contains only 'none' values, but removing such column might imply future problems calculating discounts. To ensure the correct implementation and analysis with BI tools, this column will be normalized to null values (NaN) and transformed to float32 data type. Analyzing the full worldwide dataset we observed a standard format of data (i.e. "Discount 10%), this data can be automatically transformed to percentages as decimal points, enabling a better implementation for BI tools and later numerical analysis.

After implementing all transformations there was a memory usage reduction from 2.6 mb to 2.1mb (~13%). Memory reduction is crucial in big datasets, allowing for better performance in operations, scalability and less RAM consumption.