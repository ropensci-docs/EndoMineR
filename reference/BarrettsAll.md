# Run all the basic Barrett's functions

Function to encapsulate all the Barrett's functions together. This
includes the Prague score and the worst pathological grade and then
feeds both of these things into the follow up function. The output is a
dataframe with all the original data as well as the new columns that
have been created.

## Usage

``` r
BarrettsAll(
  Endodataframe,
  EndoReportColumn,
  EndoReportColumn2,
  Pathdataframe,
  PathColumn
)
```

## Arguments

- Endodataframe:

  endoscopy dataframe of interest

- EndoReportColumn:

  Endoscopy report field of interest as a string vector

- EndoReportColumn2:

  Second endoscopy report field of interest as a string vector

- Pathdataframe:

  pathology dataframe of interest

- PathColumn:

  Pathology report field of interest as a string vector

## Value

Newdf

## See also

Other Disease Specific Analysis - Barretts Data:
[`BarrettsBxQual()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsBxQual.md),
[`BarrettsParisEMR()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsParisEMR.md),
[`Barretts_FUType()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_FUType.md),
[`Barretts_PathStage()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PathStage.md),
[`Barretts_PragueScore()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PragueScore.md)

## Examples

``` r
Barretts_df <- BarrettsAll(Myendo, "Findings", "OGDReportWhole", Mypath, "Histology")
#> Warning: There were 6 warnings in `mutate()`.
#> The first warning was:
#> ℹ In argument: `FU_Type = case_when(...)`.
#> Caused by warning:
#> ! NAs introduced by coercion
#> ℹ Run `dplyr::last_dplyr_warnings()` to see the 5 remaining warnings.
```
