# Row related

---

## Row values

 - `base::rowSums()` `base::rowMeans()`
 - `dplr::rowwise()`
 - `janitor::adorn_totals()`
 - example:
   ```R
   mutate(toca_na_sum = rowSums(is.na(across(contains("toca")))))
   ```

## Seperate Rows
- `tidyr::separte_rows()`