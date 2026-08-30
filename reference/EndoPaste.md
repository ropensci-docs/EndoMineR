# Paste endoscopy and histology results into one

As spreadsheets are likely to be submitted with pre-segregated data as
appears from endoscopy software output, these should be remerged prior
to cleaning. This function takes the column headers and places it before
each text so that the original full text is recreated. It will use the
column headers as the delimiter. This should be used before textPrep as
the textPrep function takes a character vector (ie the whole report and
not a segregated one) only

## Usage

``` r
EndoPaste(x)
```

## Arguments

- x:

  the dataframe

## Value

This returns a list with a dataframe containing one column of the merged
text and a character vector which is the delimiter list for when the
textPrep function is used

## Examples

``` r
testList<-structure(list(PatientName = c("Tom Hardy", "Elma Fudd", "Bingo Man"
), HospitalNumber = c("H55435", "Y3425345", "Z343424"), Text = c("All bad. Not good", 
"Serious issues", "from a land far away")), class = "data.frame", row.names = c(NA, -3L))
EndoPaste(testList)
#> [[1]]
#>                                                                      X1_X2_X3
#> 1     PatientName Tom Hardy\nHospitalNumber H55435\nText All bad. Not good\n 
#> 2      PatientName Elma Fudd\nHospitalNumber Y3425345\nText Serious issues\n 
#> 3 PatientName Bingo Man\nHospitalNumber Z343424\nText from a land far away\n 
#> 
#> [[2]]
#> [1] "PatientName"    "HospitalNumber" "Text"          
#> 
```
