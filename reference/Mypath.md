# Fake Pathology report

A dataset containing fake pathology reports. The report field is derived
from the whole report as follows: Mypath\<-PathDataFrameFinalColon
HistolTree\<-list('Hospital Number','Patient Name','DOB:','General
Practitioner:', 'Date of procedure:','Clinical Details:','Macroscopic
description:','Histology:','Diagnosis:',”) for(i in
1:(length(HistolTree)-1))
Mypath\<-Extractor(Mypath,'PathReportWhole',as.character(HistolTree\[i\]),
as.character(HistolTree\[i+1\]),as.character(HistolTree\[i\]))
Mypath\$Dateofprocedure\<-as.Date(Mypath\$Dateofprocedure)

## Usage

``` r
Mypath
```

## Format

A data frame with 2000 rows and 1 variables:

- PathReportWhole:

  The whole report, in text

- HospitalNumber:

  Hospital Number, in text

- PatientName:

  Patient Name, in text

- DOB:

  Date of Birth, in text

- GeneralPractitioner:

  General Practitioner, in text

- Dateofprocedure:

  Date of the procedure, as date

- ClinicalDetails:

  Clinical Details, in text

- Macroscopicdescription:

  Macroscopic description of the report, in text

- Histology:

  Histology, in text

- Diagnosis:

  Diagnosis, in text
