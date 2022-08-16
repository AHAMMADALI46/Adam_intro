# Adam_intro
/*AdaM: Analysis Data Model, Adams are developed based on TFL's tables, listings, figures Mock shells
Source: SDTM domains and sometimes we use raw datasets.
AdaMs classified into 3 categories
1. ADSL: Adam subject level information
2. Occurance/Non-BDS-----events and interventions
3. BDS----Basic Data structure/Findings

Notes: depends on study and requirements can able to create new variables in AdaM datasets where as SDTM only standard variables can create by using the Standards table.
SDTM: Dates are convert by using the ISO8601 in character forms.
Adam: All the dates are convert into numeric forms by universal way.

Dates: All dates convert into universal format (date9.) in numeric
Imputation:
if date is missign------Imputate the date---01
if date and month is missing-----Imputate the month-----01/01
categorized variables:
siteid
sitecat------trails are conducting different different sitest
SITEN--------Converting into numeric form
S01-------------1 grp
S02-------------2 grp
S03-------------3 grp

Race:
Raccat------Race character form
Racn--------Race numeric form
Asian--------1
white----------2
african--------3 etc..;

Age
Agecat-------18-85-----Age>=18 and <=65------1 group
                       Age>65--------2 grp
SEX----------F----Female & M------Male
SEXN----------1 & 2grp

ETHNIC------HISPANIC----------1grp
            NOT HISPANIC------2grp

ARM-----------Active---------1 grp
              Standard-------2grp

TRT01P---------Active-----1grp (Character)
               Standard----2grp
TRT01PN----------1 And 2. (Numeric)

ACTARM---------Active---------1grp
              Standard--------2grp

TRT01A----------Active/standard
TRT01AN----------1 and 2 grp (Numeric)

Exposure:
RFSTDTC/RFXSTDTC
RFENDTC/RFXENDTC

TRTSTDTC-------start Date and time in character
TRTSTDT----------Start date (Datepart)-----In Numeric
TRTSTM-----------Start time (Timepart)----In numeric
TRTSDTM----------Start date and time in numeric

RFENDTC/RFXENDTC

TRTENDTC----- End Date and time in character
TRTEDT----------End date (Datepart)-----In Numeric
TRTETM-----------End time (Timepart)----In numeric
TRTEDTM----------End date and time in numeric

Date Variables:
BRTHDTC-------BRTHDT
RFICDTC-------RFICDT
DTHDTC--------DTHDT
RFPENDTC-------RFPENDT
RANDDT---------RANDDT(RANDOMIZATION DATE)

Country---------Country

Population Flags:
ENRFL--------Enrollment flag
             If RFICDTC NE ' ' Then ENRFL="Y"; ELSE ENRFL="N"
SCRNFL-----Screening failure Population Flag----Subjects is not meeting eligibilty criteria.
          IF IEORRES="N" AND IECAT="INCLUSION" THEN SCRNFL="Y";
          else if IEORRES="Y" AND IECAT="EXCLUSION" THEN SCRNFL="Y";
          else SCRNFL="N";
          
          ELIGIBIL---------YES OR NO
Screen population

if ELIGIBIL="NO" Then SCRNFL="Y"
Else SCRNFL="N";


RANDFL------Random Population flag

IF DSTERM="RANDOMIZED" AND DSCAT="PROTOCOL MILESTONES" AND DSSTDTC NE ' ' THEN RANDFL="Y";
RANDDT=DSSTDTC;
else RANDFL="N";

ITTFL: Intent to treat (Ready to treat)
       IF RANDDT NE. AND RANDNO NE. THEN ITTFL="Y";
       ELSE ITTFL="N";
SAFL: SAFETY POPULATION FLAG
      subject should receive atleast one dose and one post-baseline
      IF RFXSTDTC NE ' ' then SAFL='Y';
      
COMPFL: Complete Population Flag: Whoever subjects successfully completed studies.

IF DSTERM="COMPLETED" AND DSCAT="DISPOSITION EVENT" AND EPOCH="FOLLOW-UP" AND DSS
THEN COMPFL='Y';
ELSE COMPFL="N";

FUFL
PPROTFL




Sequence No.: If it is more than one record then you have generate sequence number in SDTM and same way sub. If subject takes multiple treatements create sequence number.

For Crossover study---------subject receives multiple treatments.
101-----------Active and Standard-------1 (active), 2 (standard)
102-----------standard and active----------2(standard), 1 (active)


