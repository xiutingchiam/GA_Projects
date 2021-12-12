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