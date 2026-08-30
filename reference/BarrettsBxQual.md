# Get the number of Barrett's biopsies taken

This function gets the number of biopsies taken per endoscopy and
compares it to the Prague score for that endoscopy.Endoscopists should
be taking a certain number of biopsies given the length of a Barrett's
segment so it should be straightforward to detect a shortfall in the
number of biopsies being taken. The output is the shortfall per
endoscopist

## Usage

``` r
BarrettsBxQual(dataframe, Endo_ResultPerformed, PatientID, Endoscopist)
```

## Arguments

- dataframe:

  dataframe

- Endo_ResultPerformed:

  Date of the Endoscopy

- PatientID:

  Patient's unique identifier

- Endoscopist:

  name of the column with the Endoscopist names

## See also

Other Disease Specific Analysis - Barretts Data:
[`BarrettsAll()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsAll.md),
[`BarrettsParisEMR()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsParisEMR.md),
[`Barretts_FUType()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_FUType.md),
[`Barretts_PathStage()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PathStage.md),
[`Barretts_PragueScore()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PragueScore.md)

## Examples

``` r
# Firstly relevant columns are extrapolated from the
# Mypath demo dataset. These functions are all part of Histology data
# cleaning as part of the package.
Mypath$NumBx <- HistolNumbOfBx(Mypath$Macroscopicdescription, "specimen")
Mypath$BxSize <- HistolBxSize(Mypath$Macroscopicdescription)

# The histology is then merged with the Endoscopy dataset. The merge occurs
# according to date and Hospital number
v <- Endomerge2(
  Myendo, "Dateofprocedure", "HospitalNumber", Mypath, "Dateofprocedure",
  "HospitalNumber"
)

# The function relies on the other Barrett's functions being run as well:
b1 <- Barretts_PragueScore(v, "Findings")
#> Warning: argument is not an atomic vector; coercing
b1$PathStage <- Barretts_PathStage(b1, "Histology")

# The follow-up group depends on the histology and the Prague score for a
# patient so it takes the processed Barrett's data and then looks in the
# Findings column for permutations of the Prague score.
b1$FU_Type <- Barretts_FUType(b1, "CStage", "MStage", "PathStage")
#> Warning: There were 6 warnings in `mutate()`.
#> The first warning was:
#> ℹ In argument: `FU_Type = case_when(...)`.
#> Caused by warning:
#> ! NAs introduced by coercion
#> ℹ Run `dplyr::last_dplyr_warnings()` to see the 5 remaining warnings.


colnames(b1)[colnames(b1) == "pHospitalNum"] <- "HospitalNumber"
# The number of average number of biopsies is then calculated and
# compared to the average Prague C score so that those who are taking
# too few biopsies can be determined
hh <- BarrettsBxQual(
  b1, "Date.x", "HospitalNumber",
  "Endoscopist"
)
#> Warning: NAs introduced by coercion
#> Warning: NAs introduced by coercion
rm(v)
```
