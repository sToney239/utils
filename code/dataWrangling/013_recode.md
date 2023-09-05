# Recode

----

```R
recode_vec <- c("10" = "a", "11" = "b", "12" = "c", "13" = "d", "14" = "e")
dplyr::recode(x, !!! recode_vec)
# rename use the same `!!!`
```

### compatible with `across()`

```R
recode_col <- function(x) {
  
  recode_vec <- dat_dict |>
    filter(col_nm == cur_column()) |>
    pull(label, name = value)
  
  dplyr::recode(x, !!! recode_vec)
}
recode_col_safe <- function(x, dict) {
  recode_vec <- dict |>
    filter(col_nm == cur_column()) |>
    pull(label, name = value)
  dplyr::recode(x, !!! recode_vec)
}

data |> 
  mutate(across(all_of(cols_vec),
                \(x, dic) recode_col_safe(x, .env$dat_dict))
  )
```



https://tim-tiefenbach.de/post/2023-recode-columns/