```R
library(purrr)

unsafe_mean <- partial(mean, na.rm = TRUE)
```

```R
geom_hist_rv = partial(geom_histogram, bins = 100, color = 'white', alpha = 0.8)

# apply our function
ggplot(d) +
    geom_hist_rv(aes(x = z), fill = "tomato") +
    geom_hist_rv(aes(x = e), fill = "lightblue") +
    labs(x = "variable") +
    theme_minimal()
```

```R
# a vector of key-value pairs, species to color
peng_colors = c("Adelie" = "violet", "Chinstrap" = "goldenrod", "Gentoo" = "darkcyan")

# invoke the pairs in curried arguments
scale_color_species = partial(scale_color_manual, values = peng_colors)
scale_fill_species = partial(scale_fill_manual, values = peng_colors)

library(palmerpenguins)

ggplot(penguins) +
    aes(x = body_mass_g, y = flipper_length_mm, color = species, fill = species) +
    geom_point() +
    geom_smooth(method = "lm") +
    scale_color_species() +
    scale_fill_species()
```