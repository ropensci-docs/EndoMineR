# Clean medication column

This cleans medication column from the report assuming such a column
exists. It gets rid of common entries that are not needed. It also
splits the medication into fentanyl and midazolam numeric doses for use.
It should be used after the textPrep function.

## Usage

``` r
EndoscMeds(MedColumn)
```

## Arguments

- MedColumn:

  column of interest as a string vector

## Value

This returns a dataframe

## See also

Other Endoscopy specific cleaning functions:
[`EndoscEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/EndoscEndoscopist.md),
[`EndoscInstrument()`](https://docs.ropensci.org/EndoMineR/reference/EndoscInstrument.md),
[`EndoscopyEvent()`](https://docs.ropensci.org/EndoMineR/reference/EndoscopyEvent.md)

## Examples

``` r
MyendoNew <- cbind(EndoscMeds(Myendo$Medications), Myendo)
```
