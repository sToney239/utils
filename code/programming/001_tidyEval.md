# Tidy Eval

---

## Double Curly `{{`

```R
mutate(df, new_column = {{the_var}})
summarise(df, "mean_{{the_var}} := mean({{the_var}})") # note `:=`
```

## `enquo` + `!!`

```
mean_col <- enquo(mean_col)
mean_name <- paste0("mean_", as_label(mean_col))
summarise(df, (!!mean_name) := mean((!!mean_col)))
```