# Clean instrument column

This cleans the Instument column from the report assuming such a column
exists (where instrument usually refers to the endoscope number being
used.) It gets rid of common entries that are not needed. It should be
used after the textPrep function. Note this is possibly going to be
deprecated in the next version as the endoscope coding used here is not
widely used.

## Usage

``` r
EndoscInstrument(EndoInstrument)
```

## Arguments

- EndoInstrument:

  column of interest

## Value

This returns a character vector

## See also

Other Endoscopy specific cleaning functions:
[`EndoscEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/EndoscEndoscopist.md),
[`EndoscMeds()`](https://docs.ropensci.org/EndoMineR/reference/EndoscMeds.md),
[`EndoscopyEvent()`](https://docs.ropensci.org/EndoMineR/reference/EndoscopyEvent.md)

## Examples

``` r
Myendo$Instrument <- EndoscInstrument(Myendo$Instrument)
```
