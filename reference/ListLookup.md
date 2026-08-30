# Extract from report, using words from a list

The aim here is simply to produce a document term matrix to get the
frequency of all the words, then extract the words you are interested in
with tofind then find which reports have those words. Then find what
proportion of the reports have those terms.

## Usage

``` r
ListLookup(theframe, EndoReportColumn, myNotableWords)
```

## Arguments

- theframe:

  the dataframe,

- EndoReportColumn:

  the column of interest,

- myNotableWords:

  list of words you are interested in

## See also

Other Basic Column mutators:
[`EntityPairs_OneSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_OneSentence.md),
[`EntityPairs_TwoSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_TwoSentence.md),
[`ExtrapolatefromDictionary()`](https://docs.ropensci.org/EndoMineR/reference/ExtrapolatefromDictionary.md),
[`MyImgLibrary()`](https://docs.ropensci.org/EndoMineR/reference/MyImgLibrary.md)

## Examples

``` r
# The function relies on defined a list of
# words you are interested in and then choosing the column you are
# interested in looking in for these words. This can be for histopathology
# free text columns or endoscopic. In this example it is for endoscopic
# columns
myNotableWords <- c("arrett", "oeliac")
jj <- ListLookup(Myendo, "Findings", myNotableWords)
```
