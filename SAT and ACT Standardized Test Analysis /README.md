# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis
---

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

---

### Problem Statement

We are consultants hired by the U.S Department of Education, researching on which state(s) to assist in improving participation rates and/or scores for SAT and/or ACT so that resources can be allocated appropriately and effectively.


We will investigate the following:

- Is there any correlation between SAT/ACT participation rates and scores as well as any other external factors?
- Are there any score or participation rate bias for households with higher or lower median income?
- Does education spending play a part in higher SAT or ACT scores?


---

### Assumptions

- Median family income may not represent the full population as there are also young adults without children taking SAT/ACT.
- Public Data only reflects spending by the public education system. Data from private school is not included.
- Education spending is naturally more in states with higher population of students. Hence data for per student was included for a more accurate reflection.

---

### Datasets

#### Provided Data

The datasets used for analysis in this project are:

* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))



#### Additional Data
Additional datasets used are:

* [`median_family_income_2019.csv`](./data/median_family_income_2019.csv): 2019 Median Family Income by State (Families With At Least 1 Child Below 18 Yrs Old) ([source](https://datacenter.kidscount.org/data/tables/65-median-family-income-among-households-with-children?loc=1&loct=2#detailed/2/2-53/false/1729/any/365))
* [`Spending_by_state_2019.csv`](./data/Spending_by_state_2019.csv): 2019 Total Education Spending by State ([source](https://nces.ed.gov/programs/digest/d21/tables/dt21_236.25.asp?current=yes))
* [`Spending_by_state_per_student_2019.csv`](./data/Spending_by_state_2019.csv): 2019 Education Spending per student by State ([source](https://nces.ed.gov/programs/digest/d21/tables/dt21_236.70.asp?current=yes))

---

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|State|object|`median_family_income_2019.csv`|States where ACT and/or SAT Data is Taken|
|Spending|float|`Spending_by_state_2019.csv`|2019 Education Spending by State|
|Family Income|float|`median_family_income_2019.csv`|2019 Median Family Income by State(Families With At Least 1 Child Below 18 Yrs Old)|
|SAT Participation Rate|float|`sat_2019.csv`|SAT Participation Rate in 2019 (converted to decimal approximation)|
|ACT Participation Rate|float|`act_2019.csv`|ACT Participation Rate in 2019 (converted to decimal approximation)|
|SAT Total|float|`sat_2019.csv`|SAT Total Score in 2019|
|ACT composite|float|`act_2019.csv`|Average ACT Score in 2019|

---

### Summary of Analysis

A summary of our analysis is as follows:

**[Highest Participation Rate]**

- 2019 SAT: Rhode Island, Idaho, Michigan, Colorado, Connecticut, Delaware, Florida, Illinois
- 2019 ACT: Kentucky, Mississippi, Alabama, Montana, Nebraska, Nevada, North Carolina, Louisiana, Ohio, Oklahoma, Tennessee, Arkansas, Utah, Wisconsin, North Dakota

**[Lowest Participation Rate]**

- 2019 SAT: North Dakota, Wyoming, Wisconsin, Iowa, Mississippi, Nebraska, South Dakota
- 2019 ACT: Maine, Rhode Island, Delaware, New Hampshire, Pennsylvania

**[Highest Total/Composite Scores]**

- 2019 SAT: Minnesota, Wisconsin, South Dakota, North Dakota, Nebraska
- 2019 ACT: Massachusetts, Connecticut, New Hampshire, Rhode Island, New York

**[Lowest Total/Composite Scores]**

- 2019 SAT: West Virginia, Oklahoma, District of Columbia, Delaware, Idaho
- 2019 ACT: Nevada, Mississippi, South Carolina, Louisiana, Alabama, Oklahoma, Arizona

**[Median Family Income]**

- Highest States: Massachusetts, New Jersey, District of Columbia, Maryland, New Hampshire
- Lowest States: Mississippi, New Mexico, Arkansas, West Virginia, Louisiana

**[Total Education Spending]**

- Higest States: California, New York, Texas, Illinois, New Jersey
- Lowest States: South Dakota, Wyoming, North Dakota, Montana, Vermont

**[Education Spending Per Student]**

- Higest States: New York, District of Columbia, Vermont, New Jersey, Connecticut
- Lowest States: Idaho, Utah, Nevada, Arizona, Oklahoma

**[States with lower than average Per Student Education Spending sorted by lowest Total/Composite Scores]**
- 2019 ACT: Nevada, Mississippi, South Carolina, Louisiana, Alabama, Oklahoma
- 2019 SAT: West Virginia, Oklahoma, Idaho, Florida, Michigan

**[States with higher than average Per Student Education Spending sorted by highest Total/Composite Scores]**
- 2019 ACT: Massachusetts, Connecticut, New Hampshire, Rhode Island, New York
- 2019 SAT: North Dakota, Wyoming, Massachusetts, Vermont, Hawaii

#### Findings

- None of the states with the highest total education spending resulted in highest total/composite scores
- None of the states with the lowest total education spending resulted in lowest total/composite scores
- None of the states with the highest education spending per student resulted in highest total/composite scores
- Neveda, Oklahoma, Idaho, Arizona spent the least per student and they also produced lowest ACT/SAT total/composite scores
- Massachusetts Median Family income is one of the highest, and they scored one the highest for 2019 ACT
- District of Columbia Median Family Income is one of the highest, and they scored one the lowest for 2019 SAT
- None of the states with the lowest Median Family Income have the highest total/composite scores
- Mississippi, West Virginia, Louisiana has one of the lowest Median Family Income and they also produced lowest total/composite scores
- Delaware has one of the highest participation rate for 2019 SAT and they scored one the lowest for 2019 SAT
- Nevada, Mississippi, Alabama, Lousiana and Oklahoma has one of the highest participation rate for 2019 ACT and they scored one the lowest for 2019 ACT
- Nevada, Mississippi, Alabama, Lousiana and Oklahoma not only have one of the highest participation rate for 2019 ACT and they scored one the lowest for 2019 ACT, they also have lower than National Average Per Student Spending
- New York, North Dakota, Rhode Island, Massachusetts, Connecticut, New Hampshire were states with the highest ACT/SAT scores and their Per Student Education Spending was above the National Average Per Student Spending

#### From Visualisations

- Total Spending on Elementary/Secondary schools does not have a correlation with the participation rate/score for both SAT and ACT
- Total Spending on Elementary/Secondary schools does not have a correlation with the Median Family Income
- Spending Per Student has somewhat a positive correlation with Median Family Income
- Spending Per Student has somewhat a positive correlation with ACT Composite Score
- Spending Per Student has somewhat a negative correlation with ACT Participation Rate
- Median Family Income has a positive correlation with ACT Composite Score
- SAT Composite Score and SAT Participation Rate are negatively correlated
- ACT Composite Score and ACT Participation Rate are negatively correlated

- The trend for both ACT and SAT is the same with regard to Participation Rate vs Total/Composite Scores. Both ACT and SAT scores seem to decrease as the participation rate increases; negatively correlated.
- Median Family Income has positive correlation to ACT Composite Scores. Data seems to suggest however, that it has a negative correlation with ACT Participation Rate while a positive correlation with SAT Participation Rate.
- The Median Family Income does not have an impact on the total spending on education by states. However, as the Median Family Income increases, the spending per student by state increases; positively correlated.
- Education Spending Per Student only seem to affect ACT Composite Score. There is an increasing trend, where ACT Composite Score increases when Education Spending Per Student. Education Spending Per Student does not seem to affect the SAT Total Score or ACT/SAT Participation Rate.


---

### Conclusion

- Are there any correlation between SAT and ACT participation rates and scores as well as external factors?

Based on the data that we explored, the correlation between SAT and ACT participation rates and scores were that they were negatively correlated. So it would not be effective to work towards increasing the participation rates.
Median Family Income has positive correlation to ACT Composite Scores. Data seems to suggest however, that it has a negative correlation with ACT Participation Rate while a positive correlation with SAT Participation Rate.

- Are there any score or participation rate bias for households with higher or lower median income?

Median Family Income has positive correlation to ACT Composite Scores. Data seems to suggest however, that it has a negative correlation with ACT Participation Rate while a positive correlation with SAT Participation Rate. This is rather strange because logically, higher median family inccome should give higher scores as families will be able to afford more tuition, classes, etc.

- Does education spending play a part in higher SAT or ACT scores?

Nevada, Mississippi, Alabama, Lousiana and Oklahoma not only have one of the highest participation rate for 2019 ACT and they scored one the lowest for 2019 ACT, they also have lower than National Average Per Student Spending
New York, North Dakota, Rhode Island, Massachusetts, Connecticut, New Hampshire were states with the highest ACT/SAT scores and their Per Student Education Spending was above the National Average Per Student Spending
This shows that education spending does play a part in SAT or ACT scores.

---

### Recommendation

It does not seem to be effective to simply try to increase participation rate as high participation rate does not neccessarily translate to higher scores. However, a suggestion would be using the absolute participate instead of the participation rate. Family income is also not a factor that can be easily altered without changing other Government policies, however, it can be seen that as Median Family Income increases, the Per Student Education Spending increases. This could be due to states being more affluent and therefore, the state has more tax income to spend on education. What we can focus on as Department of Education is try to get more funding for Per Student Education Spending, particularly in the states underperforming mentioned in EDA (Nevada, Mississippi, Alabama, Lousiana and Oklahoma). 

