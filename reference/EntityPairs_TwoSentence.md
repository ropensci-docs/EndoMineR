# Look for relationships between site and event

This is used to look for relationships between site and event especially
for endoscopy events where sentences such as 'The stomach polyp was
large. It was removed with a snare' ie the therapy and the site are in
two different locations.

## Usage

``` r
EntityPairs_TwoSentence(inputString, list1, list2)
```

## Arguments

- inputString:

  The relevant pathology text column

- list1:

  The intial list to assess

- list2:

  The other list to look for

## See also

Other Basic Column mutators:
[`EntityPairs_OneSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_OneSentence.md),
[`ExtrapolatefromDictionary()`](https://docs.ropensci.org/EndoMineR/reference/ExtrapolatefromDictionary.md),
[`ListLookup()`](https://docs.ropensci.org/EndoMineR/reference/ListLookup.md),
[`MyImgLibrary()`](https://docs.ropensci.org/EndoMineR/reference/MyImgLibrary.md)

## Examples

``` r
# tbb<-EntityPairs_TwoSentence(Myendo$Findings,EventList(),HistolType())
```
