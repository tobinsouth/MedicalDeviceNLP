https://pypi.org/project/PyMedTermino/

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3289922/


https://github.com/NLPatVCU/medaCy




Here are a collection of notes during data cleaning.

## foitext2020

DATE_REPORT is NA for all elements.

#### TEXT_TYPE_CODE
D = B5 = Adverse event description 50%
E = H3 = Manufacturer’s device evaluation information <1%
N = H10 = Manufacturer’s additional adverse event narrative 49%


Example good reports:

(1) - `IT WAS REPORTED THAT THE CUSTOMER EXPERIENCED A LOW BLOOD GLUCOSE (BG) LEVEL OF BELOW 40 MG/DL. BG CAUSE WAS NOT KNOWN. CUSTOMER CONSUMED CARBOHYDRATES TO ADDRESS BG. RECOMMENDATION WAS MADE TO CONSULT WITH A HEALTHCARE PROVIDER TO DISCUSS DIABETES MANAGEMENT.`

(2) - `INFORMATION RECEIVED BY MEDTRONIC INDICATED THAT THE INSULIN PUMP HAD CRITICAL PUMP ERROR ALARM. CUSTOMER STATED THAT THERE WAS OPEN BOOK IMAGE DISPLAYED BEFORE THE CRITICAL PUMP ERROR IMAGE WAS DISPLAYED ON SCREEN. NO HARM REQUIRING MEDICAL INTERVENTION WAS REPORTED. THE INSULIN PUMP WILL BE RETURNED FOR ANALYSIS.`

Reports towards to end of 2020 have weird comma separated text:

(3) - `...9;703510725-5017879-10,I,D,333,CoreValve Evolut R TAV,EVOLUTR-34-US,C53269;703510725-5018124-10,I,D,N/A,Evolut PRO System,29mm TAV EvolutPRO-29-US,C53269;703510725-5018576-10,I,D,183,Evolut PRO System,29mm TAV EvolutPRO-29-US,C53269;703510725-5018744-10,I,D,N/A,Evolut PRO System,29mm TAV EvolutPRO-29-US,C53269;703510725-5020484-10,I,D,206,CoreValve TM Evolut TM R Transcatheter Aortic Valve...`

There are also many entries which essentially say nothing useful:

(4) - `THE RESULTS OF THE INVESTIGATION ARE INCONCLUSIVE SINCE THE DEVICE WAS NOT RETURNED FOR ANALYSIS. BASED ON THE INFORMATION RECEIVED, THE CAUSE OF THE REPORTED INCIDENT COULD NOT BE CONCLUSIVELY DETERMINED. FURTHER INFORMATION WAS REQUESTED BUT NOT RECEIVED.`



### After tokenizing
 Many tokens are a clearly identification codes:
 ['0000hrs', '0000rgebabapd', '000mcg', '00102u116', '00102u122', '00102u181', '00106u121', '00106u190', '00107u153', '00107u238', '00107u279']




 ## WOrd counts

 `[('THE', 3826693),
 ('WAS', 1860415),
 ('TO', 1078019),
 ('AND', 1061157),
 ('OF', 877303),
 ('REPORTED', 744389),
 ('NO', 708353),
 ('BE', 678462),
 ('THAT', 657873),
 ('DEVICE', 624337),
 ('NOT', 610808),
 ('PATIENT', 585455),
 ('IS', 580327),
 ('IN', 547264),
 ('FOR', 540384),
 ('INFORMATION', 471506),
 ('IT', 462053),
 ('WILL', 420368),
 ('THIS', 408211),
 ('OR', 395605),
 ('WITH', 338659),
 ('ON', 338143),
 ('EVENT', 301714),
 ('RETURNED', 298767),
 ('REPORT', 295941),
 ('PUMP', 294698),
 ('CUSTOMER', 283161),
 ('BEEN', 264387),
 ('PRODUCT', 263821),`




Using  terminology of adverse events as classified by imdrf 1657 expression

By tracking the coccurrence between of 1657 unique possible adverse events defined by the IMDRF and 1391 activity terms 


'sex' and 'intercourse' are not in that list of activities

