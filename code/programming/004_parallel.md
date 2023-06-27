```R
library(foreach)
future::plan(multisession, workers = 4)

xs <- rnorm(1000)
y <- foreach(x = xs, .export = "slow_fcn") %dofuture% {
  slow_fcn(x)
}
```