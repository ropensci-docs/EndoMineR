# Fake Endoscopies

A dataset containing fake endoscopy reports. The report fields have
already been The report field is derived from the whole report as
follows: Myendo\<-TheOGDReportFinal Myendo\$OGDReportWhole\<-gsub('2nd
Endoscopist:','Second endoscopist:',Myendo\$OGDReportWhole)
EndoscTree\<-list('Hospital Number:','Patient Name:','General
Practitioner:', 'Date of procedure:','Endoscopist:','Second
endoscopist:','Medications', 'Instrument','Extent of
Exam:','Indications:','Procedure Performed:','Findings:', 'Endoscopic
Diagnosis:') for(i in 1:(length(EndoscTree)-1))
Myendo\<-Extractor(Myendo,'OGDReportWhole',as.character(EndoscTree\[i\]),
as.character(EndoscTree\[i+1\]),as.character(EndoscTree\[i\]))
Myendo\$Dateofprocedure\<-as.Date(Myendo\$Dateofprocedure)

## Usage

``` r
Myendo
```

## Format

A data frame with 2000 rows and 1 variables:

- OGDReportWhole:

  The whole report, in text

- HospitalNumber:

  Hospital Number, in text

- PatientName:

  Patient Name, in text

- GeneralPractitioner:

  General Practitioner, in text

- Dateofprocedure:

  Date of the procedure, as date

- Endoscopist:

  Endoscopist, in text

- Secondendoscopist:

  Secondendoscopist, in text

- Medications:

  Medications, in text

- Instrument:

  Instrument, in text

- ExtentofExam:

  ExtentofExam, in text

- Indications:

  Indications, in text

- ProcedurePerformed:

  Procedure Performed, in text

- Findings:

  Endoscopic findings, in text
