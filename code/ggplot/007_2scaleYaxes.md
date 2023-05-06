2 scale y axes
================

``` r
library(tidyverse)
library(NHSRdatasets)
library(janitor, warn.conflicts = FALSE) # to clean the titles and making them snake_case

ons_mortality <- NHSRdatasets::ons_mortality

deaths_data <- ons_mortality |>
  filter(date > "2020-01-01",
         category_2 %in% c("all ages", "Yorkshire and The Humber")) |>
  pivot_wider(
    id_cols = c(date, week_no),
    values_from = counts,
    names_from = category_2
  ) |>
  clean_names()

ggplot(data = deaths_data) +
  geom_line(aes(
    x = date, 
    y = all_ages,
    col = "all ages"
  )) +
  geom_line(aes(
    x = date, 
    y = yorkshire_and_the_humber,
    col = "Yorkshire and The Humber"
  )) +
  scale_y_continuous(
    name = "Yorkshire and The Humber",
    breaks = scales::pretty_breaks(10),
    sec.axis = sec_axis(~ . * 10,
                        name = "all ages",
                        breaks = scales::pretty_breaks(10)
    )
  ) +
  scale_colour_manual(
    name = NULL,
    values = c(
      "all ages" = "#CC2200",
      "Yorkshire and The Humber" = "black"
    )
  )
```
