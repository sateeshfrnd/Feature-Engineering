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

