# Group anything by Endoscopist and returns the table

This creates a proportion table for categorical variables by endoscopist
It of course relies on a Endoscopist column being present

## Usage

``` r
CategoricalByEndoscopist(ProportionColumn, EndoscopistColumn)
```

## Arguments

- ProportionColumn:

  The column (categorical data) of interest

- EndoscopistColumn:

  The endoscopist column

## See also

Other Grouping by endoscopist:
[`MetricByEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/MetricByEndoscopist.md)

## Examples

``` r
# The function plots any numeric metric by endoscopist
# Mypath demo dataset. These functions are all part of Histology data
# cleaning as part of the package.
v <- Mypath
v$NumBx <- HistolNumbOfBx(Mypath$Macroscopicdescription, "specimen")
v$BxSize <- HistolBxSize(v$Macroscopicdescription)
# The histology is then merged with the Endoscopy dataset. The merge occurs
# according to date and Hospital number
v <- Endomerge2(
  Myendo, "Dateofprocedure", "HospitalNumber", v, "Dateofprocedure",
  "HospitalNumber"
)
# The function relies on the other Barrett's functions being run as well:
v$IMorNoIM <- Barretts_PathStage(v, "Histology")
colnames(v)[colnames(v) == "pHospitalNum"] <- "HospitalNumber"
# The function takes the column with the extracted worst grade of
# histopathology and returns the proportion of each finding (ie
# proportion with low grade dysplasia, high grade etc.) for each
# endoscopist
kk <- CategoricalByEndoscopist(v$IMorNoIM, v$Endoscopist)
rm(Myendo)
#> Warning: object 'Myendo' not found
```
