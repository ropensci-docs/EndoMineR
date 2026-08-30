# Extrapolate from Dictionary

Provides term mapping and extraction in one. Standardises any term
according to a mapping lexicon provided and then extracts the term. This
is different to the DictionaryInPlaceReplace in that it provides a new
column with the extracted terms as opposed to changing it in place

## Usage

``` r
ExtrapolatefromDictionary(inputString, list)
```

## Arguments

- inputString:

  The text string to process

- list:

  of words to iterate through

## See also

Other Basic Column mutators:
[`EntityPairs_OneSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_OneSentence.md),
[`EntityPairs_TwoSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_TwoSentence.md),
[`ListLookup()`](https://docs.ropensci.org/EndoMineR/reference/ListLookup.md),
[`MyImgLibrary()`](https://docs.ropensci.org/EndoMineR/reference/MyImgLibrary.md)

## Examples

``` r
#Firstly we extract histology from the raw report
# The function then standardises the histology terms through a series of
# regular expressions and then extracts the type of tissue 
Mypath$Tissue<-suppressWarnings(
suppressMessages(
ExtrapolatefromDictionary(Mypath$Histology,HistolType()
)
)
)
rm(MypathExtraction)
#> Warning: object 'MypathExtraction' not found
```
