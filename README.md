# gglm: Grammar of Graphics for (Generalized) Linear Model Diagnostics

## Overview

`gglm` is a package that creates beautiful `ggplot2` diagonostic plots of generalized linear models that adhere to the Grammar of Graphics and are easy to use. 

## Installation 

```{r eval = FALSE}
# Currently, the best way to install is from GitHub.
devtools::install_github("graysonwhite/gglm")
```

## Functions:

Note: not all of these functions have been built yet. `gglm` is still *very* much in a developmental stage.

`gglm()` plots the four default diagnostic plots when supplied a glm. This function works similarly to `plot.lm()`, except that it displays the four diagnostic plots at once.

`stat_normal_qq()` produces a normal Q-Q plot. This function is very similar to `stat_qq()` from `ggplot2`. 

`stat_fitted_resid()` produces a fitted vs. residual plot. 

`stat_resid_hist()` produces a histogram of the distribution of the residuals. 

`stat_scale_location()`

`stat_cook()` vs. row labels and vs. leverage/(1-leverage)

`stat_resid_leverage()`
