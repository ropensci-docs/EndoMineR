# Extracts the first test only per patient

Extracts the first test only per patient and returns a new dataframe
listing the patientID and the first test done

## Usage

``` r
SurveilFirstTest(dataframe, HospNum_Id, Endo_ResultPerformed)
```

## Arguments

- dataframe:

  dataframe

- HospNum_Id:

  Patient ID

- Endo_ResultPerformed:

  Date of the Endoscopy

## See also

Other Basic Analysis - Surveillance Functions:
[`HowManyOverTime()`](https://docs.ropensci.org/EndoMineR/reference/HowManyOverTime.md),
[`SurveilLastTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilLastTest.md),
[`SurveilTimeByRow()`](https://docs.ropensci.org/EndoMineR/reference/SurveilTimeByRow.md),
[`TimeToStatus()`](https://docs.ropensci.org/EndoMineR/reference/TimeToStatus.md)

## Examples

``` r
dd <- SurveilFirstTest(
  Myendo, "HospitalNumber",
  "Dateofprocedure"
)
```
