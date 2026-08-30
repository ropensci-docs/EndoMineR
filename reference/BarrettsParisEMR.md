# Run the Paris classification versus worst histopath grade for Barrett's

This creates a column of Paris grade for all samples where this is
mentioned.

## Usage

``` r
BarrettsParisEMR(Column, Column2)
```

## Arguments

- Column:

  Endoscopy report field of interest as a string vector

- Column2:

  Another endoscopy report field of interest as a string vector

## Value

a string vector

## See also

Other Disease Specific Analysis - Barretts Data:
[`BarrettsAll()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsAll.md),
[`BarrettsBxQual()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsBxQual.md),
[`Barretts_FUType()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_FUType.md),
[`Barretts_PathStage()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PathStage.md),
[`Barretts_PragueScore()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PragueScore.md)

## Examples

``` r
# 
Myendo$EMR<-BarrettsParisEMR(Myendo$ProcedurePerformed,Myendo$Findings)
```
