# Extract the time to an event

This function selects patients who have had a start event and an end
event of the users choosing so you can determine things like how long it
takes to get a certain outcome. For example, how long does it take to
get a patient into a fully squamous oesophagus after Barrett's ablation
for dysplasia?

## Usage

``` r
TimeToStatus(dataframe, HospNum, EVENT, indicatorEvent, endEvent)
```

## Arguments

- dataframe:

  The dataframe

- HospNum:

  The Hospital Number column

- EVENT:

  The column that contains the outcome of choice

- indicatorEvent:

  The name of the start event (can be a regular expression)

- endEvent:

  The name of the endpoint (can be a regular expression)

## See also

Other Basic Analysis - Surveillance Functions:
[`HowManyOverTime()`](https://docs.ropensci.org/EndoMineR/reference/HowManyOverTime.md),
[`SurveilFirstTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilFirstTest.md),
[`SurveilLastTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilLastTest.md),
[`SurveilTimeByRow()`](https://docs.ropensci.org/EndoMineR/reference/SurveilTimeByRow.md)

## Examples

``` r
# Firstly relevant columns are extrapolated from the
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
b1 <- Barretts_PragueScore(v, "Findings")
#> Warning: argument is not an atomic vector; coercing
b1$IMorNoIM <- Barretts_PathStage(b1, "Histology")
colnames(b1)[colnames(b1) == "pHospitalNum"] <- "HospitalNumber"

# The function groups the procedures by patient and gives
# all the procedures between
# the indicatorEvent amd the procedure just after the endpoint.
# Eg if the start is RFA and the
# endpoint is biopsies then it will give all RFA procedures and
# the first biopsy procedure

b1$EndoscopyEvent <- EndoscopyEvent(
  b1, "Findings", "ProcedurePerformed",
  "Macroscopicdescription", "Histology"
)
nn <- TimeToStatus(b1, "eHospitalNum", "EndoscopyEvent", "rfa", "dilat")
rm(v)
```
