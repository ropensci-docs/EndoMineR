# Combine all the text cleaning and extraction functions into one

This function prepares the data by cleaning punctuation, checking
spelling against the lexicons, mapping terms according to the lexicons
and lower casing everything. It contains several of the other functions
in the package for ease of use.

## Usage

``` r
textPrep(inputText, delim)
```

## Arguments

- inputText:

  The relevant pathology text columns

- delim:

  the delimitors so the extractor can be used

## Value

This returns a string vector.

## See also

Other NLP - Text Cleaning and Extraction:
[`ColumnCleanUp()`](https://docs.ropensci.org/EndoMineR/reference/ColumnCleanUp.md),
[`DictionaryInPlaceReplace()`](https://docs.ropensci.org/EndoMineR/reference/DictionaryInPlaceReplace.md),
[`Extractor()`](https://docs.ropensci.org/EndoMineR/reference/Extractor.md),
[`NegativeRemoveWrapper()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemoveWrapper.md),
[`NegativeRemove()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemove.md)

## Examples

``` r
mywords<-c("Hospital Number","Patient Name:","DOB:","General Practitioner:",
"Date received:","Clinical Details:","Macroscopic description:",
"Histology:","Diagnosis:")
CleanResults<-textPrep(PathDataFrameFinal$PathReportWhole,mywords)
```
