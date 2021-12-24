# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Ames Housing Data and Kaggle Challenge


### Problem Statement

Real estate was once considered a relative safe harbor, an asset class marked by steady value creation and predictable trends. Those days are over. New technologies and urgent sustainability concerns are now disrupting the industry in ways that raise the stakes for every decision real estate investors make.

A real estate investment trust (REITs) that operates and invests in income-producing real estate is looking into adding properties (particularly housing) in Ames, Iowa into their portfolio. As part of the REITs company's data team, we have been tasked with creating a regression model based on the Ames Housing Dataset collected from 2006 to 2010, to predict prices of houses in Ames.

---

### Background

Based on a United States Census Bureau report in 2010, Ames, Iowa had a population of approximately 59,000. Also, Ames, Iowa economy and demographics is largely defined by the Iowa State University, a public research university located in the middle of the city. More than 75% of Ames' population is either studying as a student or working as a faculty at Iowa State University, making Ames one large extended campus (more information at this website). Therefore, it isn’t surprising that Ames's largest employer is Iowa State University, which employed approximately 20% of total employment. Hence, just like many college towns, Ames' real estate market is defined by a substantial proportion of rental properties, explaining the housing market's stability in Ames. ([source](https://nycdatascience.com/blog/student-works/predicting-housing-prices-in-ames-iowa-6/))

---

### Datasets

There are 2 datasets included in the [`datasets`](../datasets/) folder for this project.

* [`train.csv`](../datasets/train.csv): (2016 - 2010) Ames Housing dataset
* [`test.csv`](../datasets/test.csv): (2016 - 2010) Ames Housing dataset, excluding target variable

---

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|State|<i>object</i>|combined_df|A state in United States of America| 
|Participation_act17|<i>float</i>|combined_df|Participation rate of ACT in 2017| 
|Composite_act17|<i>float</i>|combined_df|Aggregate composite score of participants, based on the average of English, Math, Reading and Science scores of ACT in 2017| 
|Participation_act18|<i>float</i>|combined_df|Participation rate of ACT in 2018| 
|Composite_act18|<i>float</i>|combined_df|Aggregate composite score of participants, based on the average of English, Math, Reading and Science scores of ACT in 2018| 
|Participation_act19|<i>float</i>|combined_df|Participation rate of ACT in 2019| 
|Composite_act19|<i>float</i>|combined_df|Aggregate composite score of participants, based on the average of English, Math, Reading and Science scores of ACT in 2019| 
|Participation_sat17|<i>float</i>|combined_df|Participation rate of SAT in 2017| 
|Composite_sat17|<i>float</i>|combined_df|Aggregate total score of participants, based on total score of Evidenced Based Reading and Writing (EBRW) component and Math of SAT in 2017| 
|Participation_sat18|<i>float</i>|combined_df|Participation rate of SAT in 2018| 
|Composite_sat18|<i>float</i>|combined_df|Aggregate total score of participants, based on total score of Evidenced Based Reading and Writing (EBRW) component and Math of SAT in 2018| 
|Participation_sat19|<i>float</i>|combined_df|Participation rate of SAT in 2019| 
|Composite_sat19|<i>float</i>|combined_df|Aggregate total score of participants, based on total score of Evidenced Based Reading and Writing (EBRW) component and Math of SAT in 2019|
|State|<i>object</i>|change_in_par|A state in United States of America| 
|Participation_sat17|<i>float</i>|change_in_par|Participation rate of SAT in 2017| 
|Participation_sat18|<i>float</i>|change_in_par|Participation rate of SAT in 2018| 
|Participation_sat19|<i>float</i>|change_in_par|Participation rate of SAT in 2019| 
|Participation_act17|<i>float</i>|change_in_par|Participation rate of ACT in 2017| 
|Participation_act18|<i>float</i>|change_in_par|Participation rate of ACT in 2018| 
|Participation_act19|<i>float</i>|change_in_par|Participation rate of ACT in 2019|
|Par_change_sat17to19|<i>float</i>|change_in_par|Change in participation rate in SAT from 2017 to 2019| 
|Par_change_act17to19|<i>float</i>|change_in_par|Change in participation rate in ACT from 2017 to 2019| 

---
### Conclusions and Recommendations

##### Research and Analysis
There are 3 States with notable differences in the increases and decreases in their participation rates. They are Colorado, Illinois and West Virginia.

Illinois has made SAT testing compulsory for all public high school juniors in 2018, as SAT won a multi-million-dollar contract for Illinois’ high-school tests ([*source*](https://chicago.chalkbeat.org/2018/7/27/21105418/illinois-has-embraced-the-sat-and-the-act-is-mad-about-it)). This has caused a spike in SAT participation rate by a 91% from 2017 to 2019. During the same period, there is a decline of ACT participation rate by 35%. 

Like Illinois, Colorado and the College Board has partnered to administer the SAT as the state’s accountability exam in 2017. It is now mandated that every junior will now have participate in the SAT test, and submit SAT scores to colleges as a significant part of their application([*source*](https://testive.com/colorado-sat-change-2017/)). This played a huge part in the increase of 89% in Colorado's participation rate in SAT from 2017 to 2019.

West Virginia saw an increase of 85% in the participation rate of SAT from 2017 to 2019, as SAT won the bid against ACT to become the new statewide stabdardized test for high school juniors ([*source*](https://www.wvgazettemail.com/news/education/wv-chooses-sat-as-new-high-school-standardized-test-for-juniors/article_b60d2618-4943-56f6-b180-4b4442172ef8.html)). In addition to this, West Virginia also implemented SAT school day where high school students can take the SAT tests on an allocated school day rather than on a weekend at a test center which they do not school at. Also, the cost of the test will also be offered to most public school students for free. 

A noteworthy State is Ohio, where the State saw as increase in the participation rate for both SAT and ACT. This is attributed to the Ohio State Laws, requiring all new high school graudates in 2018 and beyond to take a college admission exam. Previously, only those students and families considering going to college forked over the money to take a test designed to measure college readiness. Starting in 2018, however, Ohio joins several other states in requiring 11th graders to take either the ACT or SAT (it’s up to districts to choose which one to administer). To offset the mandate’s expense, the state will pick up the tab on testing costs([*source*](https://fordhaminstitute.org/ohio/commentary/why-requiring-juniors-take-act-or-sat-good-policy)).

Another interesting observation from the chart above is Florida, where participation was high for both tests in 2017. However, SAT participation saw an increase to 100% in 2019, while ACT participation rate saw a decline in 2018 from 66% in 2017 to 17% in 2019. Officials in Florida attributed the increase to many school districts, including those in Central Florida, offering free SAT “school day” events, where teenagers can take the exam during a regular school day with the cost covered by their schools, not their parents([*source*](https://www.orlandosentinel.com/news/education/os-ne-act-sat-florida-scores-20181024-story.html)).

##### Conclusions and Recommendations
From the analysis of the data, the SAT and ACT participation rate is mostly inversely correlated, as majority of the students will only take one test.

Based on research done on States with huge shifts in participation rates from ACT to SAT, it is observed that individual State testing policies and their collaboration with either The College Board or ACT heavily influences the participation rate in each State. When a State makes it a mandatory requirement for all graduating students to take SAT, the participation rate of SAT in that State will ultimately increase or become 100%. 

States which give options to graduating high school juniors to take either tests also saw an increase in participation rates in SAT when the exams are provided to the students for free. This is also true for States which introduced 'SAT School Day' where students can take the exam on a regular school day.

To increase participation rates, The College Board can try to replicate the successes they have with States such as Colorado, Illinois and West Virginia. The College Board can look into collaborating with States which have not made SAT a mandatory requirement for graduating high school students.

In addition, The College Board can also work with States or high schools to implement SAT School Day, and possibly look into working with them to provide free tests to the students.