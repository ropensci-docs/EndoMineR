# Extract the endoscopic event.

This extracts the endoscopic event. It looks for the event term and then
looks in the event sentence as well as the one above to see if the
location is listed. It only looks within the endoscopy fields. If tissue
is taken then this will be extracted with the HistolTypeAndSite function
rather than being listed as a result as this is cleaner and more robust.

## Usage

``` r
EndoscopyEvent(dataframe, EventColumn1, Procedure, Macroscopic, Histology)
```

## Arguments

- dataframe:

  datafrane of interest

- EventColumn1:

  The relevant endoscopt free text column describing the findings

- Procedure:

  Column saying which procedure was performed

- Macroscopic:

  Column describing all the macroscopic specimens

- Histology:

  Column with free text histology (usually microscopic histology)

## Value

This returns a character vector

## See also

Other Endoscopy specific cleaning functions:
[`EndoscEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/EndoscEndoscopist.md),
[`EndoscInstrument()`](https://docs.ropensci.org/EndoMineR/reference/EndoscInstrument.md),
[`EndoscMeds()`](https://docs.ropensci.org/EndoMineR/reference/EndoscMeds.md)

## Examples

``` r
# Myendo$EndoscopyEvent<-EndoscopyEvent(Myendo,"Findings",
# "ProcedurePerformed","MACROSCOPICALDESCRIPTION","HISTOLOGY")
```
