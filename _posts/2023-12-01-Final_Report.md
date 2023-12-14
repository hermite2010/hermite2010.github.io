---
layout: default
title: "Final Report and EDA"
author: Joseph Bradley
description: How Do the Schools Stack Up?
image: ""
---

# Intro and Motivation

In this section, I will present some of my findings about sexual crimes at Big 12 schools. My previous blog post further highlights my motivations. Know that I am driven by a desire to shed light on the significant problem occurring on campuses across the United States. To achieve this, I had to answer a crucial question: How does BYU compare to other Big 12 schools?

# Graphs

![OG Rape_graph](/assets/images/School_Rape.png)

The first graph serves as the foundation for highlighting the issue at American universities. It simply compares the number of reported rape cases each year from 2020-2022 for each of the Big 12 universities. However, this led to another question: each university has a different population size, so how does that affect the reported numbers?

![Rape10k](/assets/images/School_Rape_Per_10k.png)

This graph answers the previous question by taking into account the yearly fall enrollment size for each of the three years. It highlights how many people were affected by rape per 10,000 students on the campus. Another question arose: what about those who do not report rape incidents? How can we account for those?

![Rape_and_Potential](/assets/images/School_Rape_And_Potential.png)

This graph attempts to account for unreported rape cases. According to [RAINN](https://www.rainn.org/statistics/criminal-justice-system), only about 20% of rapes are reported for the college demographic. Thus, this graph shows the potential range of cases that could be reported on each campus over the three years.

While any number of sexual crimes is too much, the last graph is troubling, to say the least. It should be noted that rape is not the only crime being committed on these campuses. For campuses that have successfully deterred rape more than others, there still remains the crime of fondling that should be considered.

![OG_Fondling](/assets/images/School_Fondling.png)

This graph helps visualize the different Big 12 schools concerning reported fondling cases on campuses during the three years. Similar to the rape cases, how do the numbers stack up when we take enrollment into account?

![Fondling10k](/assets/images/School_Fondling_Per_10k.png)

Similar to before, this graph takes into account the enrollment of the colleges and calculates the total number of fondling cases for every 10,000 students enrolled on campus. But what about the unreported cases for fondling?

![Fondling_and_Potential](/assets/images/School_Fondling_And_Potential.png)

This graph takes the reported number as only 30% of the true total occurrences (according to [RAINN](https://www.rainn.org/statistics/criminal-justice-system)). It shows the potential total fondling cases for each campus.

![BoxPlot](/assets/images/Religious_Rape_Boxplot.png)

This graph compares reported rape cases from non-religious universities in the Big 12 to the three religious universities in the Big 12 (Brigham Young University, Texas Christian University, and Baylor University). But what happens if we account for the campus populations?

![BoxPlot10k](/assets/images/Religious_Rape_Per_10k_Boxplot.png)

This plot is shocking, to say the least. One would hope that religious universities would at least do better at preventing rape than non-religious universities.

# Findings

Based on the collected and compared data, here are the things I found most intriguing. After accounting for the campus population each year, we can really begin to see how prevalent each crime is at each campus. Seeing TCU with the highest rape count per 10,000 students was shocking. It was also surprising to me to see how high BYU ranked in fondling cases both before and after accounting for the student population. But the most shocking of all was noticing the potential total number of rapes and fondlings that could be happening on campus, but we have no way to confirm or dispute those potential numbers.

# Conclusion

I hope that the data and the visuals will help others recognize the problem before us. Whether or not schools are willing to do anything publicly about this, I encourage all to be more aware, be safe, and be proactive in preventing further sexual crimes on college campuses. Places of education and limitless potential should not become grounds for the degenerate and depraved to take advantage of others.

# Links:

The previous blog post can be found at [https://hermite2010.github.io/2023/11/30/Gathering_The_Data.html](https://hermite2010.github.io/2023/11/30/Gathering_The_Data.html).

All my code and data can be found at [https://github.com/hermite2010/Stat_386_Final_Project/tree/main](https://github.com/hermite2010/Stat_386_Final_Project/tree/main).

Check out the dashboard I made that allows you to explore the data yourself: [here](https://comparebig12crimes2023.streamlit.app/).
