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
Thankfully, all universities in the United States are required by law (The Clery Act) to record and report the crimes that are commited on or around their campuses. 
It is from these publically published reports that I got the data. 
While this work has been done mainly for a college course final project, I believe that this data can be very telling and impactful. 
This data is a collection of the sexaul assault reports combined with the violence against women reports for each of the Universities in the BIG 12 for the past three years (2022-2020).
Finding and cleaning this kind of data is a real challenge and it took me many hours to get it to work in a semi-efficient way. I hope you may learn from my mistakes. 
- [The Data](#Data)
- [Packages Galore](#Packages)
- [Step Three](#Step-Three)
- [Step Four](#Step-Four)
- [Conclusion](#Conclusion)

# The Data: What it is and where you can find it
<a name="Data"></a>
Here are the current (November 2023) urls for each of the University PDFs :

BYU https://police.byu.edu/2023-asr-provo  (page 9)

BU https://www.baylor.edu/risk/doc.php/399779.pdf (page 12)

UC https://www.uc.edu/content/dam/refresh/publicsafety-62/docs/ucpd/2023-annual-security-report.pdf (page 34)

UH http://m2s-conf.uh.edu/police/records-reports/annualreport/2023-uh-annual-security-and-fire-safety-report.pdf (page 39)

ISU https://www.police.iastate.edu/wp-content/uploads/2023/09/2022-Report-Final.pdf (page 6)

KU https://civilrights.ku.edu/sites/civilrights/files/documents/Reports/University%20of%20Kansas%20Annual%20Security%20and%20Fire%20Safety%20Report-2023-KLETC.pdf (page 60)

KSU https://www.k-state.edu/report/clery/reports/KSUCleryReport2023.pdf (page 13)

OSU https://safety.okstate.edu/police/documents/annual-security-reports/2023-annual-safety-report.pdf (page 37)

OU https://ou.edu/content/dam/OUPD/documents/safety.pdf (page 52)

TCU https://police.tcu.edu/wp-content/uploads/2023/09/TCU-Annual-Security-Report-Fire-Safety-Report_2023.v1.pdf (page 80)

TTU https://www.depts.ttu.edu/clery/reports/2023LubbockASRfinal.pdf (page 107)

UCF https://police.ucf.edu/sites/default/files/2023%20Annual%20Security%20%26%20Fire%20Safety%20Report.pdf (page 78)

UTA https://compliance.utexas.edu/sites/default/files/documents/2023-annual-security-fire-safety-report_0.pdf (page 80)

WVU https://police.wvu.edu/files/d/a1a0a6fe-444e-4353-8e92-7dcbeb00cd27/2023-annual-security-and-fire-safety-report-with-appendix.pdf (page 36)

### The Problems
While initally it might sound nice that each university has all their data in a publically available PDF, there are several problems with this. 
First off 14 different schools means 14 different and unique ways of formatting the same data. This translates to a lot of time spent on cleaning getting rid of useless information.
Secondly PDFs are a NIGHTMARE to pull data from. There are many packages and ways to try to get data from a PDF, but not all of them work on all PDFs. 
Lastly, if we really want to compare the schools to one another, we need to combine all the data together, which means making a unified format to combine them all. 

# Packages Galore
<a name="Packages"></a>

# Step Three: Visualize
<a name="Step-Three"></a>

# Step Four: Publish and Embed
<a name="Step-Four"></a>

# Conclusion
<a name="Conclusion"></a>
As data scientists, we love our data. We spend hours cleaning, manipulating, and working our data. We have amazing tools to help us do that. Unfotunately, those tools are not optimized for visualizing our data. Datawrapper is just one tool that is better suited for visualizing your data than R or Python. It is simple, straightforward, and can elevate your visualization game. Impress your coworkers, boss, and loved ones with the interactable graphics that you can now create. 

So why wait? Head over to [Datawrapper](https://app.datawrapper.de/), sign up, and start turning your data into engaging narratives today!

Happy visualizing!
