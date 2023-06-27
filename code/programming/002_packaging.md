# Packing codes

---

[Making a Simple Package in R, using Modern Tools](https://wazrak.com/making-a-simple-package-in-r-using-modern-tools/)





```R
#' base_map_plot plot china base region
# rmarkdown {r function-base_map_plot}
#'
#' @param province bool: whether plot province boundary
#' @importFrom dplyr filter
#' @importFrom ggplot2 geom_sf
#' @export
#' @return A ggplot2 object

base_map_plot <- function(province = FALSE) {
}
```

## use data/`%>%`

```R
usethis::use_data()
usethis::use_pipe()
```

## `fusen`

```R
fusen::create_fusen(path = "fusen.quickstart",
                    template = "minimal")
```

## build and install

```R
# build the tar.gz with vignettes to share with others
devtools::build(vignettes = TRUE)
# install on other devices
remotes::install_local("path/to/package/housing_0.0.0.9000.tar.gz")
```