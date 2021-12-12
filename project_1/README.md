# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university. Supporters of these standardized tests believe that they provide colleges with a broad yardstick to compare applicants across different states and background.
 
The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Until 2012, the SAT’s popularity exceeded that of the ACT. However, since then, ACT overtook SAT as the top college exam ([*source*](https://www.washingtonpost.com/blogs/answer-sheet/post/how-act-overtook-sat-as-the-top-college-entrance-exam/2012/09/24/d56df11c-0674-11e2-afff-d6c7f20a83bf_blog.html)). This sparked the College Board to revamp the SAT admission test in March 2016, in an attempt to counter the growing popularity of the ACT. 


### Problem Statement

In 2019, 64% of graduating students participated in the SAT test ([*source*](https://reports.collegeboard.org/archive/sat-suite-program-results/2019/class-2019-results)), surpassing ACT's 52% participation rate ([*source*](https://www.act.org/content/dam/act/unsecured/documents/National-CCCR-2019.pdf)). 

In order to remain as the leading provider of college entrace test, The College Board seeks to explore trends in SAT and ACT participation rates in 2017-2019 to identify the reasons for the increase in SAT participation rates since 2017, and recommend strategies on how SAT's popularity and participation rate can be futher increased.

---

### Datasets

* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))

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
