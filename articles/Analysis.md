# Analysis

  
A fundamental design principle of EndoMineR was that it should address
the important categories of questions we all have in gastroenterology,
and endoscopy in particular. These questions roughly fall into the
following: surveillance, quality and also operational questions (eg
patient flow through endoscopy).

\##**1. Surveillance functions**

  
Surveillance tracking is difficult because it relies on assessment at
several timepoint and then deciding on the next examination based on a
ruleset. A basic question is often: ’How good are our surveillance
programmes?” which really means “How good are we at making sure patients
come back in a timely way for their endoscopy after a polyp removal or
for Barrett’s surveillance”, for example?

  

![](img/EndoMineR_Surveillance.svg)

  

Surveillance relates to the timing of a test relative to other tests or
all tests done for a patient. To do this, the EndoMineR surveillance
functions simply order the endoscopies by patient and date, and extract
the date the first test was done, as well as the last test (of the same
type) and the difference in timing between each test, always grouped by
patient.

  
As all these functions are simply looking at the date of the test, they
can take a raw dataset, as long as a date column is present and use
that, rather than have a lot of pre-processing steps. Of course, the
pre-processing steps explained in the EndoMineR vignette (mainly using
the **textPrep** function) are recommended however as then the user will
be able to perform any other additional analyses if needed.

  
The basic surveillance functions are simple but are the most used.
**SurveilTimeByRow** will extract the time difference between each
individual endoscopy for an individual patient. This is useful to see
how adherent the surveillance endoscopy is to guidelines.

  

**SurveilLastTest** simply extracts the last and first test respectively
for each patient so you can assess how long the patient has been
surveilled for. This is likely to come in useful for future iterations
of EndoMineR as patient Theographs are developed (work in progress).

  

``` r

em1<-SurveilTimeByRow(Myendo,'HospitalNumber','Dateofprocedure')
```

  

| HospitalNumber | TimeSinceLast |
|:--------------:|:-------------:|
|    A1648588    |   3906 days   |
|    A1648588    |   3906 days   |
|    A1648588    |   3906 days   |
|    A1648588    |   3906 days   |
|    A1648588    |   3906 days   |

  

``` r

em3<-SurveilLastTest(Myendo,'HospitalNumber','Dateofprocedure')
```

  

| HospitalNumber | Dateofprocedure |
|:--------------:|:---------------:|
|    J1337672    |   2013-03-25    |
|    Q7176341    |   2014-05-31    |
|    M5148114    |   2014-06-18    |
|    Q7729897    |   2014-07-19    |
|    R3882435    |   2014-11-15    |

  

``` r

em4<-SurveilFirstTest(Myendo,'HospitalNumber','Dateofprocedure')
```

  

| HospitalNumber | Dateofprocedure |
|:--------------:|:---------------:|
|    F7957976    |   2001-01-03    |
|    Y8594667    |   2001-01-04    |
|    Z6299612    |   2001-01-08    |
|    R8004923    |   2001-01-15    |
|    U1759838    |   2001-01-16    |

  

Of course we may also want to know how many tests have been done over a
time period and this is provided by the function **HowManyTests**

  

This function will return the number of tests by day, month and year so
they can be easily graphed according to what you want.

  

``` r

how<-HowManyOverTime(Myendo,'Indications','Dateofprocedure','Surv')
```

  

| day | week | month | year | freq | MonthYear  |
|:---:|:----:|:-----:|:----:|:----:|:----------:|
| 25  |  4   |   1   | 2001 |  1   | 2001-01-01 |
| 27  |  4   |   1   | 2001 |  1   | 2001-01-01 |
| 23  |  12  |   3   | 2001 |  1   | 2001-03-01 |
| 11  |  15  |   4   | 2001 |  1   | 2001-04-01 |
| 20  |  16  |   4   | 2001 |  1   | 2001-04-01 |

## **2. Assessment of quality functions**

  

Quality is measured in a variety of ways. For endoscopy it is measured
according to the adherence to a) standards for endoscopic documentation
as well as b) detection of certain pathological conditions such as
dysplasia (best summarised as lesion recognition)

  

### **a) Documentation Quality**

  

As regards adherence to documentation for example, a generic function is
provided that will look up the presence of words presented in a list in
a target column. It will then output the proportion of reports that have
these words, as well as a barchart to show what proportion of the
endoscopies showed these words. The list can be comprised of terms that
should be mentioned in a report.

  

*Input*

| HospitalNumber | PatientName | Findings |
|:--:|:--:|:--:|
| J6044658 | Jargon, Victoria | No evidence of Barrett’s oesophagus, short 2 cn hiatus hernia ,Oesophageal biopsies taken from three levels as requested ,OGD today to assess for ulceration/ongoing bleeding ,Diaphragmatic pinch:40cm ,She has a small hiatus hernia ,We will re-book for 2 weeks, rebanding ,Tiny erosions at the antrum ,Biopsies taken from top of stricture-metal marking clips in situ ,The varices flattened well with air insufflation ,He is on Barrett’s Screeling List in October 2017 at St Thomas’ HALO 90 done with good effect |
| Y6417773 | Powell, Destiny | Duodenum: Duodenitis with a small erosion ,STOMACH: diffuse gastritis with angiodysplasia and punctate bleeding site on greater curve mid body - no obvious ulcer- antrum scar ?,No immediate complications ,Z-line at: 38cm - Bravo placed at 32cm- good positionat check endoscopy |
| B6072011 | Martinez-Santos, Ana | Stomach- Body Polyp- Pedunculated ,Several erosions/small ulcers in inflammed antrum ,Lax cardia with small hiatus hernia but no erosive oesophagitis ,DUODENUM: Normal to D3 |
| G1449886 | Lopez, Maria | STOMACH: Small amount of bright red blood that seems to have refluxed back through the pylorus |
| V1607560 | al-Rahimi, Rif’a | Coffee ground vomit ,OESOPHAGUS: the previous subepithelial lesion measuring 1 TTS HALO to area |
| I8031481 | Forrest, Dazheea | Stomach- Pylorus ,No cervical inlet patch |

  

In this example we are looking for the words Barrett’s and coeliac as
perhaps we have chosen the macroscopic recognition of these features to
denote what an endoscopist should always describe in the endoscopy
report:

  

``` r

library(tm)
myNotableWords <- c("barrett", "coeliac")
ListLookup(Myendo,'Findings',myNotableWords)
```

    ##        X2  Prop
    ## 1 barrett 18.05
    ## 2 coeliac  6.20

  

  

So we can see that the terms are present in the minority of reports
across endoscopists, so perhaps we can look into this further..

  

### **b) Endoscopic Quality**

#### **Sedation Usage**

  

Another measure of quality is the assessment of those factors that are
recorded at endoscopy such as degree of sedation used etc. Rather than
provide a function for each metric, again a generic function is provided
that uses any quantifiable metric and plots it against the endoscopist.
This function returns a list with two elements- the plot and the table:

  

``` r

#We have to attach the output of EndoscMeds to the original dataframe
MyendoNew<-cbind(EndoscMeds(Myendo$Medications),Myendo)
#Average Fentanyl use by endoscopist:
Mytable<-MetricByEndoscopist(MyendoNew,'Endoscopist','Fent')
```

  

|   MyendoNew.Endoscopist    | MyendoNew.Fent |
|:--------------------------:|:--------------:|
|    Dr Sullivan, Shelby     |       NA       |
|    Dr Kekich, Annabelle    |      125       |
|    Dr Sullivan, Shelby     |      125       |
| Dr Avitia-Ramirez, Alondra |       NA       |
|     Dr Greimann, Phoua     |       75       |
| Dr Avitia-Ramirez, Alondra |      150       |
|    Dr Martinez, Maegen     |      125       |
|     Dr Anderson, Alana     |       75       |
|     Dr Anderson, Alana     |       25       |
|      Dr Ives, Rashiah      |      150       |

  
  

  

## **4.Patient flow functions**

  

### **Sankey plots**

  

We often like to get an overview of how patients are flowing through a
system overall. This can give a nice visual representation of whether
which patients diverge from the normal flow through a system so we can
study them further. There are two ways to look at this. Sankey plots
give good timepoint by timepoint representation of flow. This really
works with more than one type of event at each timepoint.

  

For example, if we have a dataset with events such as ‘radiofrequency
ablation’ and ‘endoscopic mucosal resection’ or ‘nothing’ we can use the
Sankey plot to determine the order of events over a large patient
population. You choose the column in the dataframe that describes the
Procedure type (“EMR”,“RFA”,“nothing” in this case)

  

``` r

#how<-SurveySankey(Myendo,"ProcedurePerformed")
```

  

![](img/EndoMineR_Sankey.svg)

  

### **Circos plots**

  

We may need something even more aggregated. Perhaps we want to see the
overall number of patients that go from one event to another regardless
of which timepoint it is at. To do this we can use a circos plot, which
makes use of the circlize library, as follows:

``` r

#flow<-PatientFlow_CircosPlots(v,"Date.y","pHospitalNum","ProcedurePerformed")
```

  

![](img/EndoMineR_Circos.svg)

  
