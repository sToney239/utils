Functional programming
================

### double bracket: `{{`

``` r
aes(x = {{ var_name }})
```

### dot dot dot: `...`

``` r
function(data, ...) {
  ggplot(data, aes(...)) +
    geom_bar(width = 0.618) 
}

barplot_fun(mpg, class, colour = factor(cyl), !!!my_fill)
```

### add data later: `%+%`

``` r
barplot_skelly <- ggplot() +
  geom_bar(width = 0.618) +
  scale_y_continuous(expand = c(0, 0, 0.1, 0)) +
  theme(panel.grid.major.x = element_blank())

barplot_skelly %+% mpg + 
  aes(class, colour = factor(cyl), !!!my_fill) 
```

### collect parts to list

``` r
labelled_bars <- list(
  geom_bar(my_fill, width = 0.618),
  geom_text(
    stat = "count",
    aes(y     = after_stat(count), 
        label = after_stat(count), 
        fill  = NULL, colour = NULL),
    vjust = -1, show.legend = FALSE
  ),
  scale_y_continuous(expand = c(0, 0, 0.1, 0)),
  theme(panel.grid.major.x = element_blank())
)

ggplot(mpg, aes(class, colour = factor(cyl))) +
  labelled_bars +
  ggtitle("The `mpg` dataset")
```
