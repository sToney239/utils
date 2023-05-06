text
================

## label text contrast to background color

``` r
contrast <- function(colour) {
  out   <- rep("black", length(colour))
  light <- farver::get_channel(colour, "l", space = "hcl")
  out[light < 50] <- "white"
  out
}

ggplot(df, aes(row, col, fill = value)) +
  geom_raster() +
  geom_text(aes(label = round(value, 2), !!!autocontrast)) +
  coord_equal() + 
  scale_fill_viridis_c(direction =  1)
```
