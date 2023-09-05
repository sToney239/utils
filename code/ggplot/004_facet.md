facet
================

## Facetted tags

``` r
facet_wrap(~ class, scales = "free") +
  geom_label(
    data = ~ subset(.x, !duplicated(class)),
    aes(x = -Inf, y = Inf, label = LETTERS[seq_along(class)]),
    hjust = 0, vjust = 1, label.size = NA, fill = NA,
    label.padding = unit(5, "pt"),
    colour = "black"
  )
```

`ggfun` (if not facetted still usable)

```R
p + ggfun::facet_set(label=c(`0`="Zero", `1`="One"))
```
