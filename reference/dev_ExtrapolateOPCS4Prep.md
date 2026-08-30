# OPCS-4 Coding

This function extracts the OPCS-4 codes for all Barrett's procedures It
should take the OPCS-4 from the EVENT and perhaps also using extent
depending on how the coding is done. The EVENT column will need to
extract multiple findings The hope is that the OPCS-4 column will then
map from the EVENT column. This returns a nested list column with the
procedure, furthest path site and event performed

## Usage

``` r
dev_ExtrapolateOPCS4Prep(dataframe, Procedure, PathSite, Event, extentofexam)
```

## Arguments

- dataframe:

  the dataframe

- Procedure:

  The Procedure column

- PathSite:

  The column containing the Pathology site

- Event:

  the EVENT column

- extentofexam:

  the furthest point reached in the examination

## Examples

``` r
# Need to run the HistolTypeSite and EndoscopyEvent functions first here
# SelfOGD_Dunn$OPCS4w<-ExtrapolateOPCS4Prep(SelfOGD_Dunn,"PROCEDUREPERFORMED",
# "PathSite","EndoscopyEvent")
```
