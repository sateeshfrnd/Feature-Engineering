# Handling missing values 

## Introduction
The real-world data often has a lot of missing values and inherent issue in data collection, especially when working with large datasets. 

When not appropriately handled, missing data can bias the results of the machine learning models and/or reduce the accuracy of the model that leads the business to make wrong decisions.

The handling of missing data is very important during the preprocessing of the dataset as many machine learning algorithms do not support missing values.

## What is a Missing Value 
Missing value is defined as the values or data that is not stored (or not present) for some variable/s in the given dataset.

Missing Value are represented in a Dataset:
- In the dataset, the blank shows the missing values.
- In Pandas, usually missing values are represented by NaN. It stands for Not a Number.

![image](https://github.com/sateeshfrnd/Feature-Engineering/assets/8160366/98bdcc11-a03b-46e5-b388-ce711bcf45c1)

This is a sample of the missing data from the Titanic dataset. You can see the columns 'age' and 'deck' have some missing values.

## Reasons for missing data from the dataset
There can be multiple reasons why certain values are missing from the data. Reasons for the missing of data from the dataset affect the approach of handling missing data. So it’s necessary to understand why the data could be missing.
Few of the reasons :
- Data might get corrupted due to improper maintenance.
- incomplete information provided by participants/user Eg: People may have died - NAN
- non-response from those who decline to share information. Eg: Men - Salary, Women - Age 
- removal of data for confidentiality reasons 
- might be a failure in recording the values due to human error.

## Different types of Missing Data
Missing values are categorized as follows:
1. Missing Completely At Random (MCAR)
2. Missing At Random (MAR)
3. Missing Not At Random (MNAR)

### Missing Completely at Random (MCAR):
Missing completely at random (MCAR) is a type of missing data mechanism in which the probability of a value being missing is the same for all the observations. In this case, there is no relationship between the missing data and any other values observed or unobserved (the data which is not recorded) within the given dataset. That is, *missing values are completely independent of other data and there is no systematic reason for why they are missing*. There is no pattern.

For example, in a survey about the prevalence of a certain disease, the missing data might be MCAR if the survey participants with missing values for certain questions were selected randomly and their missing responses are not related to their disease status or any other variables measured in the survey.

### 2. Missing at Random MAR:
Missing at Random (MAR) is a type of missing data mechanism in which the reason for missing values can be explained by variables on which you have complete information, as *there is some relationship between the missing data and other values/data. In this case, the data is not missing for all the observations. It is missing only within sub-samples of the data, and there is some pattern in the missing values*.

Eg:
Age data :  In the survey data, you may find that all the people have answered their 'Gender', but 'Age' values are mostly missing for people who have answered their 'Gender' as 'female.' (The reason being most of the females don’t want to reveal their age.)

So, the probability of data being missing depends only on the observed value or data. In this case, the variables ‘Gender’ and ‘Age’ are related. The reason for missing values of the ‘Age’ variable can be explained by the ‘Gender’ variable, but you can not predict the missing value itself.

Income data: Suppose you are collecting income data from a group of people, but some participants choose not to report their income. If the decision to report or not report income is related to the participant's age or gender, but not to their income level, then the data is missing at random.

Medical data: Suppose you are collecting medical data on patients, including their blood pressure, but some patients do not report their blood pressure. If the patients who do not report their blood pressure are more likely to be younger or have healthier lifestyles, but the missingness is not related to their actual blood pressure values, then the data is missing at random.

### Missing data not at random (MNAR)
*Missing values depends on the value of the missing data itself*. If there is some structure/pattern in missing data and other observed data can not explain it, then it is considered to be Missing Not At Random (MNAR).

In other words, if the data is MNAR, the missingness is not random and is dependent on unobserved or unmeasured factors that are associated with the missing values.If the missing data does not fall under the MCAR or MAR, it can be categorized as MNAR.

It can happen due to the reluctance of people to provide the required information. A specific group of respondents may not answer some questions in a survey.

For example, suppose you are collecting data on the income and job satisfaction of employees in a company. If employees who are less satisfied with their jobs are more likely to refuse to report their income, then the data is not missing at random. In this case, the missingness is dependent on job satisfaction, which is not directly observed or measured.

**In the case of MNAR as well, the statistical analysis might result in bias.**
