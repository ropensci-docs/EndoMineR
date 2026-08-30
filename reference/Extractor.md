# Extract columns from the raw text

This is the main extractor for the Endoscopy and Histology report. This
relies on the user creating a list of words representing the
subheadings. The list is then fed to the Extractor so that it acts as
the beginning and the end of the regex used to split the text. Whatever
has been specified in the list is used as a column header. Column
headers don't tolerate special characters like : or ? and / and don't
allow numbers as the start character so these have to be dealt with in
the text before processing

## Usage

``` r
Extractor(inputString, delim)
```

## Arguments

- inputString:

  the column to extract from

- delim:

  the vector of words that will be used as the boundaries to extract
  against

## See also

Other NLP - Text Cleaning and Extraction:
[`ColumnCleanUp()`](https://docs.ropensci.org/EndoMineR/reference/ColumnCleanUp.md),
[`DictionaryInPlaceReplace()`](https://docs.ropensci.org/EndoMineR/reference/DictionaryInPlaceReplace.md),
[`NegativeRemoveWrapper()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemoveWrapper.md),
[`NegativeRemove()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemove.md),
[`textPrep()`](https://docs.ropensci.org/EndoMineR/reference/textPrep.md)

## Examples

``` r
# As column names cant start with a number, one of the dividing
# words has to be converted
# A list of dividing words (which will also act as column names)
# is then constructed
mywords<-c("Hospital Number","Patient Name:","DOB:","General Practitioner:",
"Date received:","Clinical Details:","Macroscopic description:",
"Histology:","Diagnosis:")
Mypath2<-Extractor(PathDataFrameFinal$PathReportWhole,mywords)
```
