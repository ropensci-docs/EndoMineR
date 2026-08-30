# Determine the Follow up group

This determines the follow up rule a patient should fit in to (according
to the British Society for Gastroenterology guidance on Barrett's
oesophagus) Specfically it combines the presence of intestinal
metaplasia with Prague score so the follow-up group can be determined.
It relies on the presence of a Prague score. It should be run after
Barretts_PathStage which looks for the worst stage of a specimen and
which will determine the presence or absence of intestinal metaplasia if
the sample is non-dysplastic. Because reports often do not record a
Prague score a more pragmatic approach as been to assess the M stage and
if this is not present then to use the C stage extrapolated using the
Barretts_Prague function

## Usage

``` r
Barretts_FUType(dataframe, CStage, MStage, IMorNoIM)
```

## Arguments

- dataframe:

  the dataframe(which has to have been processed by the
  Barretts_PathStage function first to get IMorNoIM and the
  Barretts_PragueScore to get the C and M stage if available),

- CStage:

  CStage column

- MStage:

  MStage column

- IMorNoIM:

  IMorNoIM column

## See also

Other Disease Specific Analysis - Barretts Data:
[`BarrettsAll()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsAll.md),
[`BarrettsBxQual()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsBxQual.md),
[`BarrettsParisEMR()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsParisEMR.md),
[`Barretts_PathStage()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PathStage.md),
[`Barretts_PragueScore()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PragueScore.md)

## Examples

``` r
# Firstly relevant columns are extrapolated from the
# Mypath demo dataset. These functions are all part of Histology data
# cleaning as part of the package.
# Mypath demo dataset. These functions are all part of Histology data
# cleaning as part of the package.
v <- Mypath
v$NumBx <- HistolNumbOfBx(v$Macroscopicdescription, "specimen")
v$BxSize <- HistolBxSize(v$Macroscopicdescription)
# The histology is then merged with the Endoscopy dataset. The merge occurs
# according to date and Hospital number
v <- Endomerge2(
  Myendo, "Dateofprocedure", "HospitalNumber", v, "Dateofprocedure",
  "HospitalNumber"
)
# The function relies on the other Barrett's functions being run as well:
v$IMorNoIM <- Barretts_PathStage(v, "Histology")
v <- Barretts_PragueScore(v, "Findings")
#> Warning: argument is not an atomic vector; coercing

# The follow-up group depends on the histology and the Prague score for a
# patient so it takes the processed Barrett's data and then looks in the
# Findings column for permutations of the Prague score.
v$FU_Type <- Barretts_FUType(v, "CStage", "MStage", "IMorNoIM")
#> Warning: There were 6 warnings in `mutate()`.
#> The first warning was:
#> ℹ In argument: `FU_Type = case_when(...)`.
#> Caused by warning:
#> ! NAs introduced by coercion
#> ℹ Run `dplyr::last_dplyr_warnings()` to see the 5 remaining warnings.
rm(v)
```
