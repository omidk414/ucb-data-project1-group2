# Financial Data Analysis Project

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Examples](#examples)

## Introduction

The Financial Data Analysis Project aims to provide a detailed analysis of financial data, including distributions of credit scores, annual incomes, and current loan amounts. This project was created to help financial analysts and data scientists understand the financial behaviors and characteristics of individuals. By analyzing these key metrics, the project seeks to solve problems related to financial risk assessment, creditworthiness evaluation, and strategic financial planning.

## Installation

To install and set up the Financial Data Analysis Project, follow these instructions:
```bash
pip install pandas numpy seaborn matplotlib scipy seaborn_qqplot 
```

### Prerequisites

Python 3.x
pip (Python package installer)

### Usage

To use this project, follow these steps:

  1. Clone the repository to your local machine.
  2. Navigate to the project directory.
  3. Ensure your dataset is in the correct location. This project uses m160-hw-dataset.csv located in the Resources folder.
  4. Run the main analysis script to generate visualizations and analysis reports.
      
# Example:
Below are examples of how to use the project to generate visualizations:

```
# Load your dataset
cleaned_data = pd.read_csv('Resources/cleaned_data.csv', encoding='utf-8')
```

Distribution of Credit Scores:
```
# Histogram: Illustrating distribution of Credit Score
plt.figure(figsize=(8, 5))
sns.histplot(cleaned_data['Credit Score'], bins=25, kde=True)
plt.title('Distribution of Credit Scores')
plt.show()
```

Distribution of Annual Income:
```
# Plot the distribution of annual income
sns.histplot(data['annual_income'], kde=True, bins=30)
plt.title('Distribution of Annual Income')
plt.xlabel('Annual Income')
plt.ylabel('Count')
plt.show()
```

Distribution of Current Loan Amounts:
```
# Histogram: Illustrating distribution of Current Loan Amount
plt.figure(figsize=(8, 5))
sns.histplot(cleaned_data['Current Loan Amount'], bins=25, kde=True)
plt.title('Distribution of Current Loan Amount')
plt.ylabel('Count')
plt.show()
```
