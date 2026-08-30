# Use list of endoscopic events and procedures

This function returns all the conversions from common version of events
to a standardised event list, much like the Location standardisation
function This does not include EMR as this is extracted from the
pathology so is part of pathology type.

## Usage

``` r
EventList()
```

## See also

Other NLP - Lexicons:
[`BiopsyIndex()`](https://docs.ropensci.org/EndoMineR/reference/BiopsyIndex.md),
[`GISymptomsList()`](https://docs.ropensci.org/EndoMineR/reference/GISymptomsList.md),
[`HistolType()`](https://docs.ropensci.org/EndoMineR/reference/HistolType.md),
[`LocationListLower()`](https://docs.ropensci.org/EndoMineR/reference/LocationListLower.md),
[`LocationListUniversal()`](https://docs.ropensci.org/EndoMineR/reference/LocationListUniversal.md),
[`LocationListUpper()`](https://docs.ropensci.org/EndoMineR/reference/LocationListUpper.md),
[`LocationList()`](https://docs.ropensci.org/EndoMineR/reference/LocationList.md),
[`RFACath()`](https://docs.ropensci.org/EndoMineR/reference/RFACath.md),
[`WordsToNumbers()`](https://docs.ropensci.org/EndoMineR/reference/WordsToNumbers.md)

## Examples

``` r
# unique(unlist(EventList(), use.names = FALSE))
```
