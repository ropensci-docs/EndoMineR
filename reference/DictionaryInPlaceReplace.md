# Dictionary In Place Replace

This maps terms in the text and replaces them with the standardised term
(mapped in the lexicon file) within the text. It is used within the
textPrep function.

## Usage

``` r
DictionaryInPlaceReplace(inputString, list)
```

## Arguments

- inputString:

  the input string (ie the full medical report)

- list:

  The replacing list

## Value

This returns a character vector

## See also

Other NLP - Text Cleaning and Extraction:
[`ColumnCleanUp()`](https://docs.ropensci.org/EndoMineR/reference/ColumnCleanUp.md),
[`Extractor()`](https://docs.ropensci.org/EndoMineR/reference/Extractor.md),
[`NegativeRemoveWrapper()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemoveWrapper.md),
[`NegativeRemove()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemove.md),
[`textPrep()`](https://docs.ropensci.org/EndoMineR/reference/textPrep.md)

## Examples

``` r
inputText<-DictionaryInPlaceReplace(TheOGDReportFinal$OGDReportWhole,LocationList())
```
