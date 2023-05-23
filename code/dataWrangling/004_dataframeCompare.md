# Data Frame Compare

## comparison

 - `diffdf::diffdf(df1, df2, keys="id")`
 - `dplyr::all_equal(df1, df2)`
 - `janitor::compare_df_cols(df1, df2, return = "mismatch")` (只是column type)

## duplicates

- `janitor::get_dups()`