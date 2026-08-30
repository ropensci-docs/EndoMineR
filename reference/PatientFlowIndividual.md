# Create a plot over time of patient categorical findings as a line chart

This plots the findings at endoscopy (or pathology) over time for
individual patients. An example might be with worst pathological grade
on biopsy for Barrett's oesophagus over time

## Usage

``` r
PatientFlowIndividual(
  theframe,
  EndoReportColumn,
  myNotableWords,
  DateofProcedure,
  PatientID
)
```

## Arguments

- theframe:

  dataframe

- EndoReportColumn:

  the column containing the date of the procedure

- myNotableWords:

  The terms from a column with categorical variables

- DateofProcedure:

  Column with the date of the procedure

- PatientID:

  Column with the patient's unique identifier

## See also

Other Patient Flow functions:
[`SurveySankey()`](https://docs.ropensci.org/EndoMineR/reference/SurveySankey.md)

## Examples

``` r
# This function builds chart of categorical outcomes for individal patients over time
# It allows a two dimensional visualisation of patient progress. A perfect example is 
# visualising the Barrett's progression for patients on surveillance and then
# therapy if dysplasia develops and highlighting recurrence if it happens
# Barretts_df <- BarrettsAll(Myendo, "Findings", "OGDReportWhole", Mypath, "Histology")
# myNotableWords<-c("No_IM","IM","LGD","HGD","T1a","IGD","SM1","SM2")
# PatientFlowIndividual(Barretts_df,"IMorNoIM",myNotableWords,DateofProcedure,"HospitalNumber")
# Once the function is run you should always call dev.off()
```
