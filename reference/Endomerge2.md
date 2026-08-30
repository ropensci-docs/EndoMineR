# Merge endoscopy and histology data.

This takes the endoscopy dataset date performed and the hospital number
column and merges with the equivalent column in the pathology dataset.
This is merged within a 7 day time frame as pathology is often reported
after endoscopic

## Usage

``` r
Endomerge2(x, EndoDate, EndoHospNumber, y, PathDate, PathHospNumber)
```

## Arguments

- x:

  Endoscopy dataframe

- EndoDate:

  The date the endoscopy was performed

- EndoHospNumber:

  The unique hospital number in the endoscopy dataset

- y:

  Histopathology dataframe

- PathDate:

  The date the endoscopy was performed

- PathHospNumber:

  The unique hospital number in the endoscopy dataset

## Examples

``` r
v <- Endomerge2(
  Myendo, "Dateofprocedure", "HospitalNumber",
  Mypath, "Dateofprocedure", "HospitalNumber"
)
```
