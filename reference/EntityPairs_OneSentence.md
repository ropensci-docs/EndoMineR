# See if words from two lists co-exist within a sentence

See if words from two lists co-exist within a sentence. Eg site and
tissue type. This function only looks in one sentence for the two terms.
If you suspect the terms may occur in adjacent sentences then use the
EntityPairs_TwoSentence function.

## Usage

``` r
EntityPairs_OneSentence(inputText, list1, list2)
```

## Arguments

- inputText:

  The relevant pathology text column

- list1:

  First list to refer to

- list2:

  The second list to look for

## See also

Other Basic Column mutators:
[`EntityPairs_TwoSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_TwoSentence.md),
[`ExtrapolatefromDictionary()`](https://docs.ropensci.org/EndoMineR/reference/ExtrapolatefromDictionary.md),
[`ListLookup()`](https://docs.ropensci.org/EndoMineR/reference/ListLookup.md),
[`MyImgLibrary()`](https://docs.ropensci.org/EndoMineR/reference/MyImgLibrary.md)

## Examples

``` r
# tbb<-EntityPairs_OneSentence(Mypath$Histology,HistolType(),LocationList())
```
