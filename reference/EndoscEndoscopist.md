# Clean endoscopist column

If an endoscopist column is part of the dataset once the extractor
function has been used this cleans the endoscopist column from the
report. It gets rid of titles It gets rid of common entries that are not
needed. It should be used after the textPrep function

## Usage

``` r
EndoscEndoscopist(EndoscopistColumn)
```

## Arguments

- EndoscopistColumn:

  The endoscopy text column

## Value

This returns a character vector

## See also

Other Endoscopy specific cleaning functions:
[`EndoscInstrument()`](https://docs.ropensci.org/EndoMineR/reference/EndoscInstrument.md),
[`EndoscMeds()`](https://docs.ropensci.org/EndoMineR/reference/EndoscMeds.md),
[`EndoscopyEvent()`](https://docs.ropensci.org/EndoMineR/reference/EndoscopyEvent.md)

## Examples

``` r
Myendo$Endoscopist <- EndoscEndoscopist(Myendo$Endoscopist)
```
