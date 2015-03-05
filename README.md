## Building vignette

The easiest way to build the vignette for the moment is to launch R from main
directory of the ProfilesMetagene package. The R version should be `R/R-3.1.1`

From R:
```
library(packrat)
packrat::on()
packrat::extlib("devtools")
packrat::extlib("knitr")
build()
```
