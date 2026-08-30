# Plot a metric by endoscopist

This takes any of the numerical metrics in the dataset and plots it by
endoscopist. It of course relies on a Endoscopist column being present

## Usage

``` r
MetricByEndoscopist(dataframe, Column, EndoscopistColumn)
```

## Arguments

- dataframe:

  The dataframe

- Column:

  The column (numeric data) of interest

- EndoscopistColumn:

  The endoscopist column

## See also

Other Grouping by endoscopist:
[`CategoricalByEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/CategoricalByEndoscopist.md)

## Examples

``` r
#The function gives a table with any numeric
# metric by endoscopist
# In this example we tabulate medication by
# endoscopist
# Lets bind the output of EndoscMeds to the main dataframe so we
# have a complete dataframe with all the meds extracted
MyendoNew<-cbind(EndoscMeds(Myendo$Medications),Myendo)

# Now lets look at the fentanly use per Endoscopist:
kk<-MetricByEndoscopist(MyendoNew,'Endoscopist','Fent')
#EndoBasicGraph(MyendoNew, "Endoscopist", "Fent") #run this
#if you want to see the graph
rm(Myendo)
#> Warning: object 'Myendo' not found
```
