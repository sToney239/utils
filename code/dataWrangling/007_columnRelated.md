# Column Related

---

## Speed Comparison

```R
# faster, but only create at the right-most position
mtcars_tbl$year <- 1974L
# slower
mutate(mtcars_tbl, year = 1974L)
```

## Selection

```R
cols <- c("hp", "wt")

mtcars_tbl[cols] # faster
select(mtcars_tbl, all_of(cols)) # slower
# note `all_of(vars)`
```

## Pull

```R
mtcars_tbl[["hp"]] # fastest
pull(mtcars_tbl, hp) # faster
mtcars_tbl$hp # slowest
```

## Create dummy variable

```R
pivot_wider(df, names_from = nominal_var, values_from = 1, values_fill = 0)
```