Data Imputation
================

## with zero or mean

``` r
mutate(
  imputed_zero = replace(Age, is.na(Age), 0),
  imputed_mean = replace(Age, is.na(Age),  mean(titanic_train$Age, na.rm = TRUE))
)
```

## use MICE (Multivariate Imputation via Chained Equations)

``` r
mice_imputed <- data.frame(
  original = titanic_train$Age,
  # pmm: Predictive mean matching.
  imputed_pmm = complete(mice(titanic_numeric, method = "pmm"))$Age,
  # cart: Classification and regression trees.
  imputed_cart = complete(mice(titanic_numeric, method = "cart"))$Age,
  # laso.norm: Lasso linear regression.
  imputed_lasso = complete(mice(titanic_numeric, method = "lasso.norm"))$Age
)
```

## use missForest

``` r
library(missForest)

missForest_imputed <- data.frame(
  original = titanic_numeric$Age,
  imputed_missForest = missForest(titanic_numeric)$ximp$Age
)
```
