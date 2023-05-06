Useful Packages
================

## mix effect model

- [lme4](https://github.com/lme4/lme4) :Mixed-effects models in R
  - **negative binomial** mixed model using the Laplace approximation,
    which is known not to be optimal, so use GLMMadaptive, and use
    `GLMMadaptive::marginal_coefs()`
- [fixest](https://lrberge.github.io/fixest/reference/index.html) : Fast
  and user-friendly fixed-effects estimation
- [modelr](https://padpadpadpad.github.io/post/bootstrapping-non-linear-regressions-with-purrr/):
  modeling functions working with pipe
- [fwildclusterboot](https://s3alfisc.github.io/fwildclusterboot/):
  multiple fast wild cluster bootstrap
- [simpr](https://statisfactions.github.io/simpr/index.html): tidy
  sampling
- [gratia](https://cran.r-project.org/web/packages/gratia/vignettes/gratia.html):
  ggplot-mgcv(GAM) visualization
- [GLMMadaptive](https://drizopoulos.github.io/GLMMadaptive/index.html):
  Generalized Linear Mixed Models
  - using the adaptive Gauss-Hermite quadrature rule
  - but only accept 1 random effect
- [inla](https://www.r-inla.org/learnmore/books)

## ggplot

- [ggsflabel](https://github.com/yutannihilation/ggsflabel) : map
  labelling
- [ggredist](https://alarm-redist.org/ggredist/): blue-red map coloring
- [memoise](https://memoise.r-lib.org/index.html): save function call
  cashes
- [ggigraph](https://davidgohel.github.io/ggiraph/): create dynamic and
  interactive graphics
- [showtext](https://cran.rstudio.com/web/packages/showtext/vignettes/introduction.html):
  Using Fonts More Easily in R Graphs
- [ragg](https://ragg.r-lib.org/): R based on the AGG library developed
  by the late Maxim Shemanarev. AGG provides both higher performance and
  higher quality than the standard raster devices provided by grDevices.

## sj-family (from [StrengeJacke](https://github.com/strengejacke?tab=repositories))

- [sjmisc](https://strengejacke.github.io/sjmisc/index.html) - Data and
  Variable Transformation Functions
- [sjstats](https://strengejacke.github.io/sjstats/index.html) - Common
  Statistical Computation Functions
- [sjPlot](https://strengejacke.github.io/sjPlot/index.html) - Data
  Visualization for Statistics in Social Science
- [ggeffects](https://strengejacke.github.io/ggeffects/) - Estimated
  Marginal Means and Adjusted Predictions from Regression Models
- [parameters](https://easystats.github.io/parameters/index.html) -
  Describe and understand your model’s parameters!

## spatial

- [osm history
  data](https://cran.r-project.org/web/packages/ohsome/vignettes/ohsome.html)

## R-package

- [usethis project workflow](https://usethis.r-lib.org/):automates
  repetitive tasks that arise during project setup and development, both
  for R packages and non-package projects.
- [Rmd write package](https://jacobbien.github.io/litr-project/): write
  a complete R package in a single R markdown document
