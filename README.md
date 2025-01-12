## Project - Mental Health in the Tech Industry

**Objectives**
- Practice performing EDA using Pandas.
- Practice visualizing data with Matplotlib & Seaborn.
- Practice estimating population parameters from sample data and communicating uncertainty around your insights.

*As this data set has more than 100 different questions, only part of questions were selected to be used in analysis.*


**IMPORTANT: plotly.express is used for graphs in this work. To see them, Notebook has to be run locally**


**Work is divided in folowing steps:**

I. Data preparation

II. Data cleanup

III. Overview of the respondents sociodemographic features
1. Respondents overview by **Age**
2. Respondents overview by **Gender**
3. Respondents overview by **Race**
4. Respondents overview by **Live_country** and **Work_country**:
5. Company overview

IV. Exploratory data analysis
1. How employee mental health changes over time? Can current condition be predicted by family history or medical history?
2. How mental health is perceived comparing to physical health?
3. How potential mental health issues may affect work and carreer?

V. Prevalence rate for 3 selected disorders

VI. Summary

VII. Structure

### I. Data preparation
As not all questions will be used for analysis, only chossen ones will be selected from data base. For more convenient analysis, data is transformed for more convenient form. In case there were several answers from the same user - they were joined to one answer. e.g. Question id 115 for current mental health disorders


### II. Data cleanup
- Data type for most of the columns were changed to represent better information in that column.
- **Age** outliers were changed to Na value.
- **Gender** was grouped into 3 groups: "Female", "Male", "Other". 
- Na values check shows that survey was not consistent: not the same questions were used every year.


### III. Overview of the respondents sociodemographic features
#### 1. Respondents overview by **Age**
- Additional **Age_category** column was created to have grouping by age.
- Basic descriptive statistics show average respondet **Age** at ~34-35 years, with only in 2014 being at 32 years.
- Distribution in age groups is similar in first 3 Surveys, however in the last years there is tendency of lower level of participation of younger respondents.

#### 2. Respondents overview by **Gender**
- Most of respondents **Gender** is Male with about 4-1, 3-1 ratio compared to **Female**. 
- Over the years, as total number of respondens decreases, gap becomes smaller with about 2-1 ratio.

#### 3. Respondents overview by **Race**
- Around 57% of respondents are **White**
- Around 37% of respondens didn't answer to this question. This could be one of the topics for further analysis, to see how **Race** is related to answers to other questions.

#### 4. Respondents overview by **Live_country** and **Work_country**
- **Work_country** data was not collected in year 2014. There for, this year was excluded from this analysis part.
- For years where both **Live_country** and **Work_country** data is avalable majority of respondens stated that they live and work in the same country.
- There are 50 respondents stating that they live and work in different countries.
- Most respondents stated that they Live and/or Work in United States of America, with United Kingdom and Canada going next. This suggests that online survey is more known / more used by North America employees.

#### 5. Company overview
- Majority of respondents are not self employed. 
- In 2016 and folowing surveys, **Self employed** respondends were not answering question regarding **Company size**.
- Self employed respondents tend to work in smaller companies.
- Survey respondents are working mainly in tech companies.
- Company size grouping is not equal / consistent, there for - biased, as it gives impression of higher frequency of specific company size, which is impacted by bigger range of that group.
- Nearly 25% of respondends working in not tech company has primary role related to tech. 
- More than 10% respondens work in the biggest, non tech companies, with role related to tech, which implies that usually bigger companies tend to have resources dedicated to specific field / topics, in this case - tech.


### IV. Exploratory data analysis
#### 1. How employee mental health changes over time? Can current condition be predicted by family history or medical history?
- About 20 % of respondents answered "Yes" to all questions (current and previous diagnosis, family history, etc.).
- About 7 % answered "No" to all questions (current and previous diagnosis, family history, etc.).
- Nearly 30 % of respondents prefer not to answer the question if have they been diagnosed with Mental Health disorder.
- **Chi-squared statistics** and **p-value** were calculated for each pair to check is there a relationship between them. It showed strong association between family history, previous treatments, and current condition.

#### 2. How mental health is perceived comparing to physical health?
- Correlation coeficient of 0.78 shows strong relationship between how importance on mental and physical health is perceived.  
- Majority of respondents do not see negative consequences discussing mental and physical health.
- Tendency is that respondents think there will more be negative consequences discussing mental health compared to physical health.
- Tendencies to see negative consequences increase with increasing **Age**.
- Even though company is providing Mental health benefit as part of healthcare coverage, it seems like respondends do not know if Mental and Physical health is treated the same. It would be interesting to investigate if this is relate to *Communication topic* or more *Trust* topic.

#### 3. How potential mental health issues may affect work and carreer?
Analysis for this question was done on data where respondets answered that they currently have MH disorder (question id = 33).
- Answers show importance of treating MH disorders effectively, as this may lead to less impact on work.
- However, when asked if productivity is affected by MH disorder, majority of respondents choose not to answer this question. This may signal lack of trust in work enviroment. The ones who answered - stated that productivity is affected by MH disorder. 
- When asked directly about MH impact to career, most respondents did not answer. However from the ones who answered it seems that impact was rather negative than positive.
- Respondens see overall support for MH disorders from employers rather neutral - towards negative.


### V. Prevalence rate for 3 selected disorders
***Prevalance rate** is the proportion of a particular population found to be affected by a medical condition / disease / or a risk factor at a specific time.*
- **Prevalence rate** for this data set is quite high. E.g. for Anxiety more than 34 % for Female, ~20 % for Male. In overall population ~ 300 mln out of 8000 mln have Anxiety. This makes ~ 3.75 % of population. Results here are impacted by data sourse - voluntary survey in OSMI web page. One of the reasons may be, that respondens who already have MH disorder were answering this survey more frequently. This makes data strongly biased.
- **Confidence intervals** is a range in which the actual prevalence will fall with the 95 % confidence.
- There is different **Prevalence rate** of having MH disorder depending on **Gender**. It would be interesting topic for further analysis to check Causation. 


### VI. Summary
#### Survey itself
- It was not perfomed yearly. Data from 2015 is not available.
- Number of respondens have decreasing tendency from ~1400 to ~350. Not sufficient sample size can have impact on results.
- Not the same questions were used every year, which makes analysis more complicated.
- There is no information about how representative is sample in regards to **Age**, **Gender**, **Race** and other features.
- Data collectione method - online questionair in OSMI page implies that respondents are the ones who are interested / related to Mental Health. This results in overestimation of MH.

#### Sociodemographics
- Tipical respondent from this data is white male, living in North AMerica, working in relatively big Tech company, and primary role related to tech.
- Because of sampling bias, this data is not representative to provide generealised insights about Mental healf (MH) of population.
- Before making inference about MH of employees in tech companies, sociodemographic information (using weighting) should be adjusted. 
- Information about distribution of MH in tech companies has to be collected to have correct conclusions.


### VII. Structure
mental_health.ipynb: Jupyter Notebook file for data analysis.

README.md: Provides an overview and instructions for the project.

mental_health.sqlite: Data sourse for analysis.

requirements.txt: Provides list of packages to be installed what will be needed for anlysis.

```
pip install -r requirements.txt
```