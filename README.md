
# gglm: Grammar of Graphics for (Generalized) Linear Model Diagnostics

## Overview

`gglm` is a package that creates beautiful `ggplot2` diagonostic plots
of generalized linear models that adhere to the Grammar of Graphics and
are easy to use.

## Installation

``` r
# Currently, the best way to install is from GitHub.
devtools::install_github("graysonwhite/gglm")
```

## Examples

`gglm` has two main goals: (1) quickly create the four main diagnostics
plots, similarly to when you call `plot()` on an `lm` or `glm` type
object, and (2) produce diagnostic plots the align with the Grammar of
Graphics by creating `ggplot2` layers that allow for easy plotting of
particular model diagnostic plots.

### Example 1: Quickly creating the four diagnostic plots

``` r
library(gglm)
library(ggplot2)
data(mtcars) # Load example data
m1 <- lm(mpg ~ ., data = mtcars) # Create your model

gglm(m1)
```

![](README_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

### Example 2: Using the Grammar of Graphics

``` r
library(gglm) 
library(broom) 
library(ggplot2)
data(mtcars) # Load example data
model <- lm(mpg ~ ., data = mtcars) # Create your model
model_tbl <- broom::augment(m1) # Turn model output into a tidy tibble

ggplot(data = model_tbl) +
  stat_scale_location()
```

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

## Function List

`gglm()` plots the four default diagnostic plots when supplied a glm.
This function works similarly to `plot.lm()`, except that it displays
the four diagnostic plots at once.

`stat_normal_qq()` produces a normal Q-Q plot. This function is very
similar to `stat_qq()` from `ggplot2`.

`stat_fitted_resid()` produces a fitted vs. residual plot.

`stat_resid_hist()` produces a histogram of the distribution of the
residuals.

`stat_scale_location()`

`stat_cook()` vs. row labels and vs. leverage/(1-leverage). (Not yet
built)

`stat_resid_leverage()` (Not yet built)
