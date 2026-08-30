# Extract the Prague score

The aim is to extract a C and M stage (Prague score) for Barrett's
samples. This is done using a regex where C and M stages are explicitly
mentioned in the free text Specfically it extracts the Prague score

## Usage

``` r
Barretts_PragueScore(dataframe, EndoReportColumn, EndoReportColumn2)
```

## Arguments

- dataframe:

  dataframe with column of interest

- EndoReportColumn:

  column of interest

- EndoReportColumn2:

  second column of interest

## See also

Other Disease Specific Analysis - Barretts Data:
[`BarrettsAll()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsAll.md),
[`BarrettsBxQual()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsBxQual.md),
[`BarrettsParisEMR()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsParisEMR.md),
[`Barretts_FUType()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_FUType.md),
[`Barretts_PathStage()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PathStage.md)

## Examples

``` r
# The example takes the endoscopy demo dataset and searches the
# Findings column (which contains endoscopy free text about the
# procedure itself). It then extracts the Prague score if relevant. I
# find it easiest to use this on a Barrett's subset of data rather than
# a dump of all endoscopies but of course this is a permissible dataset
# too


aa <- Barretts_PragueScore(Myendo, "Findings", "OGDReportWhole")
```
