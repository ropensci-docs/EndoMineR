# Create a Sankey plot for patient flow

The purpose of the function is to provide a Sankey plot which allows the
analyst to see the proportion of patients moving from one state (in this
case type of Procedure) to another. This allows us to see for example
how many EMRs are done after RFA.

## Usage

``` r
SurveySankey(dfw, ProcPerformedColumn, PatientID)
```

## Arguments

- dfw:

  the dataframe extracted using the standard cleanup scripts

- ProcPerformedColumn:

  the column containing the test like P rocPerformed for example

- PatientID:

  the column containing the patients unique identifier eg hostpital
  number

## See also

Other Patient Flow functions:
[`PatientFlowIndividual()`](https://docs.ropensci.org/EndoMineR/reference/PatientFlowIndividual.md)

## Examples

``` r
names(Myendo)[names(Myendo) == "HospitalNumber"] <- "PatientID"
gg <- SurveySankey(Myendo, "ProcedurePerformed", "PatientID")
#> starting httpd help server ...
#>  done
```
