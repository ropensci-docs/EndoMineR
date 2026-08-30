# Extract the number of biopsies taken from the histology report

This extracts the number of biopsies taken from the pathology report.
This is usually from the Macroscopic description column. It collects
everything from the regex \[0-9\]1,2.0,3 to whatever the string boundary
is (z).

## Usage

``` r
HistolNumbOfBx(inputString, regString)
```

## Arguments

- inputString:

  The input text to process

- regString:

  The keyword to remove and to stop at in the regex

## See also

Other Histology specific cleaning functions:
[`HistolBxSize()`](https://docs.ropensci.org/EndoMineR/reference/HistolBxSize.md),
[`HistolTypeAndSite()`](https://docs.ropensci.org/EndoMineR/reference/HistolTypeAndSite.md)

## Examples

``` r
qq <- HistolNumbOfBx(Mypath$Macroscopicdescription, "specimen")
```
