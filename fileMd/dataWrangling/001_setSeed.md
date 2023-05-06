set seed
================

``` r
withr::with_seed(seed = 123,
                 h("Bruno"))
h3 <- function(..., seed){
  withr::with_seed(seed = seed,
                   h(...))
}
```
