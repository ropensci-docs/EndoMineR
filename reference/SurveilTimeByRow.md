# Extract the time difference between each test in days

This determines the time difference between each test for a patient in
days It returns the time since the first and the last study as a new
dataframe.

## Usage

``` r
SurveilTimeByRow(dataframe, HospNum_Id, Endo_ResultPerformed)
```

## Arguments

- dataframe:

  dataframe,

- HospNum_Id:

  Patient ID

- Endo_ResultPerformed:

  Date of the Endoscopy

## See also

Other Basic Analysis - Surveillance Functions:
[`HowManyOverTime()`](https://docs.ropensci.org/EndoMineR/reference/HowManyOverTime.md),
[`SurveilFirstTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilFirstTest.md),
[`SurveilLastTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilLastTest.md),
[`TimeToStatus()`](https://docs.ropensci.org/EndoMineR/reference/TimeToStatus.md)

## Examples

``` r
aa <- SurveilTimeByRow(
  Myendo, "HospitalNumber",
  "Dateofprocedure"
)
```
