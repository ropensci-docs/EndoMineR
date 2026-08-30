# Get the worst pathological stage for Barrett's

This extracts the pathological stage from the histopathology specimen.
It is done using 'degradation' so that it will look for the worst
overall grade in the histology specimen and if not found it will look
for the next worst and so on. It looks per report not per biopsy (it is
more common for histopathology reports to contain the worst overall
grade rather than individual biopsy grades). Specfically it extracts the
histopathology worst grade within the specimen FOr the sake of accuracy
this should alwats be used after the HistolDx function and this removes
negative sentences such as 'there is no dysplasia'. This current
function should be used on the column derived from HistolDx which is
called Dx_Simplified

## Usage

``` r
Barretts_PathStage(dataframe, PathColumn)
```

## Arguments

- dataframe:

  dataframe with column of interest

- PathColumn:

  column of interest

## See also

Other Disease Specific Analysis - Barretts Data:
[`BarrettsAll()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsAll.md),
[`BarrettsBxQual()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsBxQual.md),
[`BarrettsParisEMR()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsParisEMR.md),
[`Barretts_FUType()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_FUType.md),
[`Barretts_PragueScore()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PragueScore.md)

## Examples

``` r
# Firstly relevant columns are extrapolated from the
# Mypath demo dataset. These functions are all part of Histology data
# cleaning as part of the package.
# The function then takes the Histology column from the merged data set (v).
# It extracts the worst histological grade for a specimen
b <- Barretts_PathStage(Mypath, "Histology")
rm(v)
#> Warning: object 'v' not found
```
