# Determine the largest biopsy size from the histology report

This extracts the biopsy size from the report. If there are multiple
biopsies it will extract the overall size of each one (size is
calculated usually in cubic mm from the three dimensions provided). This
will result in row duplication.

## Usage

``` r
HistolBxSize(MacroColumn)
```

## Arguments

- MacroColumn:

  Macdescrip

## Details

This is usually from the Macroscopic description column.

## See also

Other Histology specific cleaning functions:
[`HistolNumbOfBx()`](https://docs.ropensci.org/EndoMineR/reference/HistolNumbOfBx.md),
[`HistolTypeAndSite()`](https://docs.ropensci.org/EndoMineR/reference/HistolTypeAndSite.md)

## Examples

``` r
rr <- HistolBxSize(Mypath$Macroscopicdescription)
```
