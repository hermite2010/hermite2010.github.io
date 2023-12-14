---
layout: default
title: "Getting Data to Compare the BIG XII Sex Offenses"
author: Joseph Bradley
description: Learning how to Scrap PDFs without getting PTSD
---
# Motivation
I am a student at BYU, where we recently joined the BIG 12 conference with 13 other schools for the 2023 football season. 
Because everyone here at BYU made such a huge deal about BYU joining the BIG 12 conference, I thought it fitting to compare the 14 schools against one another. 
But because I am not much of a sports-person, I thought that I could look at the sexual assualt and violence against women that happens on or around the school campuses. 

Sexual assualt is a big problem, and something I feel passionate about. I would hope that we can eliminate all sexual crimes across all college campuses in America. Any amount of sexual crime is too much. Another reason I am passionate about this is because of the religious foundation on which BYU is built, and I would expect this to help reduce the overall sexual crime that would happen on BYU's campus. So I wanted to check and see how BYU compared to other similar campuses. 
Thankfully, all universities in the United States are required by law (The Clery Act) to record and report the crimes that are commited on or around their campuses. 
It is from these publically published reports that I got the data. 

While this work has been done mainly for a college course final project, I believe that this data can be very telling and impactful. 
This data is a collection of the sexaul assault reports combined with the violence against women reports for each of the Universities in the BIG 12 for the past three years (2022-2020).
Finding and cleaning this kind of data is a real challenge and it took me many hours to get it to work in a semi-efficient way. I hope you may learn from my mistakes. 
- [Ethical](#Ethical)
- [The Data](#Data)
- [Cleaning](#Cleaning)
- [Conclusion](#Conclusion)

# Ethical Statement
<a name="Ethical"></a>
It is important that the data used in data science is ethically obtained and ethically used. The data I collected and compiled is publically available, and there are no permissions necessary to view the school reports on their crimes. I am also trying to use this data ethically. I do not intend to make any specific school look bad, blame them, or cast shame on them. This data and project is primarily for making a specific problem (Campus sexual crimes) easier to see and understand. My hope is that this data can help people make moral decisions to help reduce the amount of sexual crimes that happen on college campuses around the world.  


# The Data: What it is and where you can find it
<a name="Data"></a>
As mentioned before, each university is required by law to report the crimes that happen on their campuses. Each university publishes the most recent report somewhere on their respective websites. Here are the current (November 2023) urls for each of the University PDFs :

[BYU](https://police.byu.edu/2023-asr-provo)(page 9), [BU](https://www.baylor.edu/risk/doc.php/399779.pdf)(page 12), [UC](https://www.uc.edu/content/dam/refresh/publicsafety-62/docs/ucpd/2023-annual-security-report.pdf)(page 34), [UH](http://m2s-conf.uh.edu/police/records-reports/annualreport/2023-uh-annual-security-and-fire-safety-report.pdf)(page 39), [ISU](https://www.police.iastate.edu/wp-content/uploads/2023/09/2022-Report-Final.pdf)(page 6), [KU](https://civilrights.ku.edu/sites/civilrights/files/documents/Reports/University%20of%20Kansas%20Annual%20Security%20and%20Fire%20Safety%20Report-2023-KLETC.pdf)(page 60), [KSU](https://www.k-state.edu/report/clery/reports/KSUCleryReport2023.pdf)(page 13), [OSU](https://safety.okstate.edu/police/documents/annual-security-reports/2023-annual-safety-report.pdf)(page 37), [OU](https://ou.edu/content/dam/OUPD/documents/safety.pdf)(page 52), [TCU](https://police.tcu.edu/wp-content/uploads/2023/09/TCU-Annual-Security-Report-Fire-Safety-Report_2023.v1.pdf)(page 80), [TTU](https://www.depts.ttu.edu/clery/reports/2023LubbockASRfinal.pdf)(page 107), [UCF](https://police.ucf.edu/sites/default/files/2023%20Annual%20Security%20%26%20Fire%20Safety%20Report.pdf)(page 78), [UTA](https://compliance.utexas.edu/sites/default/files/documents/2023-annual-security-fire-safety-report_0.pdf)(page 80), [WVU](https://police.wvu.edu/files/d/a1a0a6fe-444e-4353-8e92-7dcbeb00cd27/2023-annual-security-and-fire-safety-report-with-appendix.pdf)(page 36)

## The Problems
While initally it might sound nice that each university has all their data in a publically available PDF, there are several problems with this. 
First off 14 different schools means 14 different and unique ways of formatting the same data. This translates to a lot of time spent on cleaning getting rid of useless information.
Secondly PDFs are a NIGHTMARE to pull data from, if you are familiar with webscrapping, it might seem simple to scrape the data tables off of each pdf and call it good. This is not the case working with PDFs. There are many packages and ways to try to get data from a PDF, but not all of them work on all PDFs. 
Lastly, if we really want to compare the schools to one another, we need to combine all the data together, which means making a unified format to combine them all. 

## Packages Galore
<a name="Packages"></a>
Here I will list some of the Python packages that I tried to use, but that ultimately did not work in getting the data from the pdfs. 

PDFMiner, PyPDF2, Tabula, PyMuPDF, Tika, and Textract.

As I mentioned, none of these worked for me. They either could not get all of the data, or they just failed to work at all. Thankfully, I did find a package that worked wonders, and nobody online was talking about it at all: Camelot

Camelot is also one of the easiest pdf packages to use. Here is a link to [Camelot's](https://camelot-py.readthedocs.io/en/master/) documentation if you are curious. If you are looking at the code on my github, you will notice how I use camelot to get all of the data for this project. 

Here is an example of my code in how I used Camelot:
```python
import camelot
import pandas as pd

BYU_table = camelot.read_pdf('BYU_report.pdf', pages='9,10', flavor='stream')
```
It is incredibly simple, and worked well enough for me. 

# Cleaning The Data
<a name="Cleaning"></a>
So, after successcully using camelot to extract the necessary data from their respective PDF's, it was time to clean. Part of the miracle of Camelot is also part of it's curse. The reason Camelot worked so well was because it grabbed most of the text on the page and formatted it into a table. That table then becomes a very large cleaning project. I had to identify the rows and the columns that contain the actual data I want, and extract them from the mother table. Then there were often different typos or text based error that I had to remove or work around to make sure I retain the years and the crimes commited. So there was a lot of table manipulations, melting, pivoting, and merging in order to get all the data from each school into a uniform format to make a master data table. For example, this was one of the easier data tables to clean: 

```python
### BYU ###
# take only rows we need
BYU_sexOff = BYU_table[0].df.iloc[[1,9,10,11,12]]
BYU_VAWA = BYU_table[1].df.iloc[[2,4,5,6]]
# take out columns we don't need
BYU_sexOff = BYU_sexOff.drop([2,4,6], axis=1)
BYU_VAWA = BYU_VAWA.drop([2,4,6], axis=1)
# reset the index
BYU_sexOff = BYU_sexOff.reset_index(drop=True)
BYU_VAWA = BYU_VAWA.reset_index(drop=True)
# make the first row the column names
BYU_sexOff.columns = BYU_sexOff.iloc[0]
BYU_VAWA.columns = BYU_VAWA.iloc[0]
# drop the first row
BYU_sexOff = BYU_sexOff.drop([0])
BYU_VAWA = BYU_VAWA.drop([0])
# reset the index
BYU_sexOff = BYU_sexOff.reset_index(drop=True)
BYU_VAWA = BYU_VAWA.reset_index(drop=True)
# Adding the year counts together
BYU_sexOff['2020 Total'] = BYU_sexOff['2020'].astype(int).sum(axis = 1)
BYU_sexOff['2021 Total'] = BYU_sexOff['2021'].astype(int).sum(axis = 1)
BYU_sexOff['2022 Total'] = BYU_sexOff['2022'].astype(int).sum(axis = 1)
BYU_VAWA['2020 Total'] = BYU_VAWA['2020'].astype(int).sum(axis = 1)
BYU_VAWA['2021 Total'] = BYU_VAWA['2021'].astype(int).sum(axis = 1)
BYU_VAWA['2022 Total'] = BYU_VAWA['2022'].astype(int).sum(axis = 1)
# Add the school name
BYU_sexOff['School'] = 'BYU'
BYU_VAWA['School'] = 'BYU'
# Keep only the columns we want
BYU_sexOff = BYU_sexOff[['Year Reported','School','2020 Total','2021 Total','2022 Total']]
BYU_VAWA = BYU_VAWA[['Year Reported','School','2020 Total','2021 Total','2022 Total']]
# Rename Year Reported to Offense
BYU_sexOff = BYU_sexOff.rename(columns={'Year Reported': 'Offense'})
BYU_VAWA = BYU_VAWA.rename(columns={'Year Reported': 'Offense'})

# Combine the two BYU tables
BYU_sexOff = pd.concat([BYU_sexOff,BYU_VAWA])
# Reset the index
BYU_sexOff = BYU_sexOff.reset_index(drop=True)
```
This code gave us this output:


|    | Offense           | School   |   2020 |   2021 |   2022 |
|---:|:------------------|:---------|-------:|-------:|-------:|
|  0 | Rape              | BYU      |      4 |      7 |      6 |
|  1 | Fondling          | BYU      |     10 |     13 |     17 |
|  2 | Incest            | BYU      |      0 |      0 |      0 |
|  3 | Statutory Rape    | BYU      |      0 |      0 |      0 |
|  4 | Domestic Violence | BYU      |      0 |      2 |      1 |


I also felt that looking at the data in a few different ways was appropriate. I sought to account for each schools respective campus enrollment to see the crime count per capita. I also tried to account for the unreported crimes. While each publication of the campus crimes comes with a statment about hom many crimes they think have gone unreported, according to the [Rape, Abuse & Incest National Network](https://www.rainn.org/statistics/criminal-justice-system), only about 20-32% of the rapes are reported in college age student. And about 60% of all sexual assaults don't get reported. I wanted to try to visualise what the numbers would look like if what was reported was only a percentage of the real numbers.

Here is a snippit of what the final data set looks like:


|    | School   |   Year |   Dating Violence |   Domestic Violence |   Fondling |   Incest |   Rape |   Stalking |
|---:|:---------|-------:|------------------:|--------------------:|-----------:|---------:|-------:|-----------:|
|  0 | BU       |   2020 |                 4 |                   7 |         13 |        0 |     13 |         17 |
|  1 | BU       |   2021 |                 5 |                   8 |         10 |        0 |     20 |         23 |
|  2 | BU       |   2022 |                 0 |                  13 |          8 |        0 |     22 |         40 |
|  3 | BYU      |   2020 |                 5 |                   0 |         10 |        0 |      4 |         14 |
|  4 | BYU      |   2021 |                 5 |                   2 |         13 |        0 |      7 |          6 |



# Conclusion
<a name="Conclusion"></a>
Overall, finding the data was easy, obtaining the data was incredibly difficult, but I believe the potential for this data is significant. My hope is that this project can make people really start to understand the gravity of the sexual safety on campuses, even religiously endorsed campuses, and encourage people to get more involved in helping make campuses a better place for students to learn and live life. You can view my own results in my next blog post, [Final Report and EDA](https://hermite2010.github.io/2023/12/01/Final_Report.html).
