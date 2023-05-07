# Packing codes

---

## `fusen`

```R
fusen::create_fusen(path = "fusen.quickstart",
                    template = "minimal")
```

## use data/`%>%`

```R
usethis::use_data()
usethis::use_pipe()
```

## build and install

```R
# build the tar.gz with vignettes to share with others
devtools::build(vignettes = TRUE)
# install on other devices
remotes::install_local("path/to/package/housing_0.0.0.9000.tar.gz")
```