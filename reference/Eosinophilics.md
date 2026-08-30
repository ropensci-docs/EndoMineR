# Extract the Prague score

The aim is to extract a C and M stage (Prague score) for Barrett's
samples. This is done using a regex where C and M stages are explicitly
mentioned in the free text Specfically it extracts the Prague score

## Usage

``` r
Eosinophilics(dataframe, findings, histol, IndicationsFroExamination)
```

## Arguments

- dataframe:

  dataframe with column of interest

- findings:

  column of interest

- histol:

  second column of interest

- IndicationsFroExamination:

  second column of interest

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


aa <- Eosinophilics(v, "Findings", "Histology","Indications")
```
