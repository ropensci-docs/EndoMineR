# Tidy up messy columns

This does a general clean up of whitespace, semi-colons,full stops at
the start of lines and converts end sentence full stops to new lines.

## Usage

``` r
ColumnCleanUp(vector)
```

## Arguments

- vector:

  column of interest

## Value

This returns a character vector

## See also

Other NLP - Text Cleaning and Extraction:
[`DictionaryInPlaceReplace()`](https://docs.ropensci.org/EndoMineR/reference/DictionaryInPlaceReplace.md),
[`Extractor()`](https://docs.ropensci.org/EndoMineR/reference/Extractor.md),
[`NegativeRemoveWrapper()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemoveWrapper.md),
[`NegativeRemove()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemove.md),
[`textPrep()`](https://docs.ropensci.org/EndoMineR/reference/textPrep.md)

## Examples

``` r
ii<-ColumnCleanUp(Myendo$Findings)
```
