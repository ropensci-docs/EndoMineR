# Clean html endoscopic images

This is used to pick and clean endoscopic images from html exports so
they can be prepared before being linked to pathology and endoscopy
reports

## Usage

``` r
MyImgLibrary(file, delim, location)
```

## Arguments

- file:

  The html report to extract (the html will have all the images
  references in it)

- delim:

  The phrase that separates individual endoscopies

- location:

  The folder containing the actual images

## See also

Other Basic Column mutators:
[`EntityPairs_OneSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_OneSentence.md),
[`EntityPairs_TwoSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_TwoSentence.md),
[`ExtrapolatefromDictionary()`](https://docs.ropensci.org/EndoMineR/reference/ExtrapolatefromDictionary.md),
[`ListLookup()`](https://docs.ropensci.org/EndoMineR/reference/ListLookup.md)

## Examples

``` r
# MyImgLibrary("~/Images Captured with Proc Data Audit_Findings1.html",
#                         "procedureperformed","~/")
```
