# Wrapper for Negative Remove

This performs negative removal on a per sentance basis

## Usage

``` r
NegativeRemoveWrapper(inputText)
```

## Arguments

- inputText:

  the text to remove Negatives from

## Value

This returns a column within a dataframe. This should be changed to a
character vector eventually

## See also

Other NLP - Text Cleaning and Extraction:
[`ColumnCleanUp()`](https://docs.ropensci.org/EndoMineR/reference/ColumnCleanUp.md),
[`DictionaryInPlaceReplace()`](https://docs.ropensci.org/EndoMineR/reference/DictionaryInPlaceReplace.md),
[`Extractor()`](https://docs.ropensci.org/EndoMineR/reference/Extractor.md),
[`NegativeRemove()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemove.md),
[`textPrep()`](https://docs.ropensci.org/EndoMineR/reference/textPrep.md)

## Examples

``` r
# Build a character vector and then
# incorporate into a dataframe
anexample<-c("There is no evidence of polyp here",
"Although the prep was poor,there was no adenoma found",
"The colon was basically inflammed, but no polyp was seen",
"The Barrett's segment was not biopsied",
"The C0M7 stretch of Barrett's was flat")
anexample<-data.frame(anexample)
names(anexample)<-"Thecol"
# Run the function on the dataframe and it should get rid of sentences (and
# parts of sentences) with negative parts in them.
#hh<-NegativeRemoveWrapper(anexample$Thecol)
```
