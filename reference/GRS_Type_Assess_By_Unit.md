# Create GRS metrics by endoscopist (X-ref with pathology)

This extracts the polyps types from the data (for colonoscopy and
flexible sigmoidosscopy data) and outputs the adenoma,adenocarcinoma and
hyperplastic detection rate by endoscopist as well as overall number of
colonoscopies. This will be extended to other GRS outputs in the future.

## Usage

``` r
GRS_Type_Assess_By_Unit(dataframe, ProcPerformed, Endo_Endoscopist, Dx, Histol)
```

## Arguments

- dataframe:

  The dataframe

- ProcPerformed:

  The column containing the Procedure type performed

- Endo_Endoscopist:

  column containing the Endoscopist name

- Dx:

  The column with the Histological diagnosis

- Histol:

  The column with the Histology text in it

## Examples

``` r
nn <- GRS_Type_Assess_By_Unit(
  vColon, "ProcedurePerformed",
  "Endoscopist", "Diagnosis", "Original.y"
)
```
