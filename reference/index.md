# Package index

## NLP - Text Cleaning and Extraction:

Functions to clean raw text

- [`textPrep()`](https://docs.ropensci.org/EndoMineR/reference/textPrep.md)
  : Combine all the text cleaning and extraction functions into one
- [`Extractor()`](https://docs.ropensci.org/EndoMineR/reference/Extractor.md)
  : Extract columns from the raw text
- [`DictionaryInPlaceReplace()`](https://docs.ropensci.org/EndoMineR/reference/DictionaryInPlaceReplace.md)
  : Dictionary In Place Replace
- [`NegativeRemove()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemove.md)
  : Remove negative and normal sentences
- [`NegativeRemoveWrapper()`](https://docs.ropensci.org/EndoMineR/reference/NegativeRemoveWrapper.md)
  : Wrapper for Negative Remove
- [`spellCheck()`](https://docs.ropensci.org/EndoMineR/reference/spellCheck.md)
  : Find and Replace
- [`ColumnCleanUp()`](https://docs.ropensci.org/EndoMineR/reference/ColumnCleanUp.md)
  : Tidy up messy columns
- [`ListLookup()`](https://docs.ropensci.org/EndoMineR/reference/ListLookup.md)
  : Extract from report, using words from a list

## NLP - Text merging:

Functions to help merge datasets

- [`EndoPaste()`](https://docs.ropensci.org/EndoMineR/reference/EndoPaste.md)
  : Paste endoscopy and histology results into one
- [`Endomerge2()`](https://docs.ropensci.org/EndoMineR/reference/Endomerge2.md)
  : Merge endoscopy and histology data.

## NLP - Lexicons:

Basic lexicons

- [`HistolType()`](https://docs.ropensci.org/EndoMineR/reference/HistolType.md)
  : Use list of pathology types
- [`LocationList()`](https://docs.ropensci.org/EndoMineR/reference/LocationList.md)
  : Use list of upper and lower GI standard locations
- [`LocationListUpper()`](https://docs.ropensci.org/EndoMineR/reference/LocationListUpper.md)
  : Use list of standard locations for upper GI endoscopy
- [`LocationListUniversal()`](https://docs.ropensci.org/EndoMineR/reference/LocationListUniversal.md)
  : Use list of standard locations for upper GI endoscopy
- [`LocationListLower()`](https://docs.ropensci.org/EndoMineR/reference/LocationListLower.md)
  : Use list of standard locations for lower GI endoscopy
- [`RFACath()`](https://docs.ropensci.org/EndoMineR/reference/RFACath.md)
  : Use list of catheters used in radiofrequency ablation
- [`EventList()`](https://docs.ropensci.org/EndoMineR/reference/EventList.md)
  : Use list of endoscopic events and procedures
- [`BiopsyIndex()`](https://docs.ropensci.org/EndoMineR/reference/BiopsyIndex.md)
  : Index biopsy locations
- [`GISymptomsList()`](https://docs.ropensci.org/EndoMineR/reference/GISymptomsList.md)
  : Index of GI symptoms
- [`WordsToNumbers()`](https://docs.ropensci.org/EndoMineR/reference/WordsToNumbers.md)
  : Convetr words to numbers especially for the histopathology text

## Basic Column mutators

Basic Column mutators

- [`ExtrapolatefromDictionary()`](https://docs.ropensci.org/EndoMineR/reference/ExtrapolatefromDictionary.md)
  : Extrapolate from Dictionary
- [`ListLookup()`](https://docs.ropensci.org/EndoMineR/reference/ListLookup.md)
  : Extract from report, using words from a list
- [`EntityPairs_OneSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_OneSentence.md)
  : See if words from two lists co-exist within a sentence
- [`EntityPairs_TwoSentence()`](https://docs.ropensci.org/EndoMineR/reference/EntityPairs_TwoSentence.md)
  : Look for relationships between site and event
- [`MyImgLibrary()`](https://docs.ropensci.org/EndoMineR/reference/MyImgLibrary.md)
  : Clean html endoscopic images

## Specific Text Cleaning - Endoscopy specific cleaning functions:

Functions to help clean endoscopy reports

- [`EndoscEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/EndoscEndoscopist.md)
  : Clean endoscopist column
- [`EndoscInstrument()`](https://docs.ropensci.org/EndoMineR/reference/EndoscInstrument.md)
  : Clean instrument column
- [`EndoscMeds()`](https://docs.ropensci.org/EndoMineR/reference/EndoscMeds.md)
  : Clean medication column
- [`EndoscopyEvent()`](https://docs.ropensci.org/EndoMineR/reference/EndoscopyEvent.md)
  : Extract the endoscopic event.

## Specific Text Cleaning - Histology specific cleaning functions:

Functions to help clean histology text

- [`HistolNumbOfBx()`](https://docs.ropensci.org/EndoMineR/reference/HistolNumbOfBx.md)
  : Extract the number of biopsies taken from the histology report
- [`HistolBxSize()`](https://docs.ropensci.org/EndoMineR/reference/HistolBxSize.md)
  : Determine the largest biopsy size from the histology report
- [`HistolTypeAndSite()`](https://docs.ropensci.org/EndoMineR/reference/HistolTypeAndSite.md)
  : Extract the site a specimen was removed from as well as the type

## Basic Analysis Helper - Grouping by endoscopist

Grouping by endoscopist

- [`MetricByEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/MetricByEndoscopist.md)
  : Plot a metric by endoscopist
- [`CategoricalByEndoscopist()`](https://docs.ropensci.org/EndoMineR/reference/CategoricalByEndoscopist.md)
  : Group anything by Endoscopist and returns the table

## Basic Analysis - Surveillance Functions:

Functions to analyse surveillance intervals

- [`SurveilTimeByRow()`](https://docs.ropensci.org/EndoMineR/reference/SurveilTimeByRow.md)
  : Extract the time difference between each test in days
- [`SurveilLastTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilLastTest.md)
  : Extract the last test done by a patient only
- [`SurveilFirstTest()`](https://docs.ropensci.org/EndoMineR/reference/SurveilFirstTest.md)
  : Extracts the first test only per patient
- [`TimeToStatus()`](https://docs.ropensci.org/EndoMineR/reference/TimeToStatus.md)
  : Extract the time to an event
- [`HowManyOverTime()`](https://docs.ropensci.org/EndoMineR/reference/HowManyOverTime.md)
  : Number of tests done per month and year by indication

## Disease Specific Analysis - Barretts Data

Functions for reading and writing Barretts Data.

- [`BarrettsAll()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsAll.md)
  : Run all the basic Barrett's functions
- [`BarrettsBxQual()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsBxQual.md)
  : Get the number of Barrett's biopsies taken
- [`BarrettsParisEMR()`](https://docs.ropensci.org/EndoMineR/reference/BarrettsParisEMR.md)
  : Run the Paris classification versus worst histopath grade for
  Barrett's
- [`Barretts_FUType()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_FUType.md)
  : Determine the Follow up group
- [`Barretts_PathStage()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PathStage.md)
  : Get the worst pathological stage for Barrett's
- [`Barretts_PragueScore()`](https://docs.ropensci.org/EndoMineR/reference/Barretts_PragueScore.md)
  : Extract the Prague score

## Disease Specific Analysis - Polyp functions:

Polyp analysis

- [`GRS_Type_Assess_By_Unit()`](https://docs.ropensci.org/EndoMineR/reference/GRS_Type_Assess_By_Unit.md)
  : Create GRS metrics by endoscopist (X-ref with pathology)

## Patient Flow functions:

Visualise patient flow

- [`SurveySankey()`](https://docs.ropensci.org/EndoMineR/reference/SurveySankey.md)
  : Create a Sankey plot for patient flow
- [`PatientFlow_CircosPlots()`](https://docs.ropensci.org/EndoMineR/reference/PatientFlow_CircosPlots.md)
  : Create a Circos plot for patient flow
- [`PatientFlowIndividual()`](https://docs.ropensci.org/EndoMineR/reference/PatientFlowIndividual.md)
  : Create a plot over time of patient categorical findings as a line
  chart

## Data overview:

Basic consort diagrams

- [`sanity()`](https://docs.ropensci.org/EndoMineR/reference/sanity.md)
  : Create a basic consort diagram from dataframes

## Data Presentation helpers:

Functions to help with data visualisation

- [`theme_Publication()`](https://docs.ropensci.org/EndoMineR/reference/theme_Publication.md)
  : Set the publication theme for all the ggplots
- [`scale_fill_Publication()`](https://docs.ropensci.org/EndoMineR/reference/scale_fill_Publication.md)
  : Set the fills for all the ggplots
- [`scale_colour_Publication()`](https://docs.ropensci.org/EndoMineR/reference/scale_colour_Publication.md)
  : Set the colour theme for all the ggplots
- [`EndoBasicGraph()`](https://docs.ropensci.org/EndoMineR/reference/EndoBasicGraph.md)
  : Basic graph creation using the template specified in
  theme_Publication.
