Basic plots
================

I'm an R Markdown document!

Section 1
=========

Here's a **code chunk** that samples from a *normal distribution*:

``` r
samp = rnorm(100)
length(samp)
```

    ## [1] 100

Section 2
=========

I can take the mean of the sample, too! The mean is -0.0093189.

The purpose of this file is to present a couple of basic plots using `ggplot`.

First we create a dataframe containing variables for our plots.

``` r
set.seed(1234)

plot_df = tibble(
  x = rnorm(1000, sd = .5),
  y = 1 + 2 * x + rnorm(1000)
)
```

First we show a histogram of the `x` variable.

``` r
ggplot(plot_df, aes(x = x)) + geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](plot_example_files/figure-markdown_github/x_hist-1.png)

Next we show a scatterplot of `y` vs `x`.

``` r
ggplot(plot_df, aes(x = x, y = y)) + geom_point()
```

![](plot_example_files/figure-markdown_github/yx_scatter-1.png)
