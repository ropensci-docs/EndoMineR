# Remove negative and normal sentences

Extraction of the negative sentences so that normal findings can be
removed and not counted when searching for true diseases. eg remove 'No
evidence of candidal infection' so it doesn't get included if looking
for candidal infections. It is used by default as part of the textPrep
function but can be turned off as an optional parameter

## Usage

``` r
NegativeRemove(inputText)
```

## Arguments

- inputText:

  column of interest

## Value

This returns a column within a dataframe. THis should be changed to a
character vector eventually

## See also

Other NLP - Text Cleaning and Extraction:
[`ColumnCleanUp()`](https://docs.ropensci.org/EndoMineR/reference/ColumnCleanUp.md),
[`DictionaryInPlaceReplace()`](https://docs.ropensci.org/EndoMineR/reference/DictionaryInPlaceReplace.md),
[`Extractor()`](https://docs.ropensci.org/EndoMineR/reference/Extractor.md),
[`NegativeRemoveWrapper()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemoveWrapper.md),
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
hh<-NegativeRemove(anexample$Thecol)
```
