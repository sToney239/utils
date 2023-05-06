Color Scales
================

## Setting midpoints in divergent scales

``` r
scale_colour_gradientn(
    colours = my_palette, 
    limits = ~ c(-1, 1) * max(abs(.x))
  )
```
