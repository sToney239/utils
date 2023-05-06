# Filter technique

---

## Speed Comparison

```R
vctrs::vec_slice(mtcars_tbl, mtcars_tbl$hp > 100) # fastest
mtcars_tbl[mtcars_tbl$hp > 100, ] # normal
filter(mtcars_tbl, filter(hp > 100) # slowest
```

## Filter empty rows
 - `dplyr::filter(!(dplyr::if_all(everything(), ~ is.na(.x))))`
 - `express::drop_empty_rows()`
 - `janitor::remove_empty("rows")`
 - `janitor::remove_constant()`