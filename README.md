The FDA ADVERSE EVENT REPORTING SYSTEM (FAERS) database contains adverse event reports, medication error reports and product quality complaints resulting in adverse events that were submitted to FDA.
This data FAERS daa consists of following tables:

1.	"DEMO" table contains patient demographic and administrative information, a single record for each event report.
2.	"DRUG" table contains drug/biologic information for as many medications as were reported for the event (1 or more per event).
3.	"OUT" contains patient outcomes for the event (0 or more).
4.	"REAC" table contains all "Medical Dictionary for Regulatory Activities" (MedDRA) terms coded for the event (1 or more). For more information on MedDRA, please contact: TRW, VAR 1/6A/MSSO, 12011 Sunset Hills Road, Reston, VA 20190-3285, USA; website is www.meddramsso.com.

This are the tables used for vizualisations in PowerBI and also gained the valuable insights from the data.

New Table Using DAX:
Created a new table called "PatientsByAgeGroup" from the "demo" table using "age" column.
DAX query : AgeGroup = SWITCH(TRUE(), demo[age] < 5, "Under 5", demo[age] < 18, "5-18", demo[age] < 50, "18-50", demo[age] < 75, "50-75", demo[age] < 95, "76-90", "Undefined")
