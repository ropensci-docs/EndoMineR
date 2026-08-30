# Basic graph creation using the template specified in theme_Publication.

This creates a basic graph using the template specified in
theme_Publication. It takes a numeric column and plots it against any
non-numeric x axis in a ggplot

## Usage

``` r
EndoBasicGraph(dataframe, xdata, number)
```

## Arguments

- dataframe:

  dataframe

- xdata:

  The x column

- number:

  The numeric column

## Value

Myplot This is the final plot

Myplot

## See also

Other Data Presentation helpers:
[`scale_colour_Publication()`](https://docs.ropensci.org/EndoMineR/reference/scale_colour_Publication.md),
[`scale_fill_Publication()`](https://docs.ropensci.org/EndoMineR/reference/scale_fill_Publication.md),
[`theme_Publication()`](https://docs.ropensci.org/EndoMineR/reference/theme_Publication.md)

## Examples

``` r
# This function plots numeric y vs non-numeric x
# Get some numeric columns e.g. number of biopsies and size
Mypath$Size <- HistolBxSize(Mypath$Macroscopicdescription)
Mypath$NumBx <- HistolNumbOfBx(Mypath$Macroscopicdescription, "specimen")
Mypath2 <- Mypath[, c("NumBx", "Size")]
EndoBasicGraph(Mypath, "Size", "NumBx")
#> Warning: `legend.margin` must be specified using `margin()`
#> ℹ For the old behavior use `legend.spacing`
#> `geom_smooth()` using formula = 'y ~ x'
```
