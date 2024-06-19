# Financial Data Analysis Project

## Table of Contents

- [Financial Data Analysis Project](#financial-data-analysis-project)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Project Overview](#project-overview)
  - [Environment Setup](#environment-setup)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Usage](#usage)
    - [Dataset](#dataset)
    - [Example:](#example)
  - [Collaboration](#collaboration)
  - [Acknowledgements](#acknowledgements)

## Introduction

The Financial Data Analysis Project aims to provide a detailed analysis of financial data, including distributions of credit scores, annual incomes, and current loan amounts. This project was created to help financial analysts and data scientists understand the financial behaviors and characteristics of individuals. By analyzing these key metrics, the project seeks to solve problems related to financial risk assessment, creditworthiness evaluation, and strategic financial planning.

## Project Overview

This project includes:

   - Data loading and preprocessing
   - Various visualizations to explore the data
   - Statistical analysis to understand relationships between variables
   - Insights on financial risk and creditworthiness

## Environment Setup

Clone the repository to your local machine:
```
git clone https://github.com/omidk414/ucb-data-project1-group2.git
cd <repository-directory>
```

## Installation

To install and set up the Financial Data Analysis Project, follow these instructions:
```
# Install the required packages:
pip install pandas numpy seaborn matplotlib scipy seaborn_qqplot
```

### Prerequisites

Python 3.x
pip (Python package installer)

Seaborn and SciPy Libraries

### Usage

To use this project, follow these steps:

  1. Clone the repository to your local machine.
  2. Navigate to the project directory.
  3. Ensure your dataset is in the correct location. This project uses m160-hw-dataset.csv located in the Resources folder.
  4. Run the main analysis script to generate visualizations and analysis reports.

### Dataset 
Link to retrieve original dataset:
- [m160-hw-dataset.csv](https://github.com/scetx/datax/blob/master/01-data-x-fundamentals/m160-titanic/m160-hw-dataset.csv) 
      
# Example:
Below are examples of how to use the project to generate visualizations:

```
# Load your dataset
cleaned_data = pd.read_csv('Resources/cleaned_data.csv', encoding='utf-8')
```

Hexbin Plot for Annual Income vs Credit Score for all of the Loan Status data
```
plt.figure(figsize=(10, 6))
plt.hexbin(cleaned_data['Annual Income'], cleaned_data['Credit Score'], gridsize=30, cmap='Blues', mincnt=1)
cb = plt.colorbar(label='Count')
plt.xlabel('Annual Income')
plt.ylabel('Credit Score')
plt.title('Hexbin Plot of Annual Income vs. Credit Score')
xticks = plt.gca().get_xticks()
plt.gca().set_xticklabels(['{:.1f}M'.format(x / 1e6) for x in xticks])
plt.show()
```

Color Gradient by Density
```
plt.figure(figsize=(10, 6))
sns.kdeplot(x=cleaned_data['Annual Income'], y=cleaned_data['Credit Score'], cmap='Blues', shade=True, thresh=0.05)
plt.xlabel('Annual Income') 
plt.ylabel('Credit Score')
plt.title('Density Plot of Annual Income vs. Credit Score')
xticks = plt.gca().get_xticks()
plt.gca().set_xticklabels(['{:.1f}M'.format(x / 1e6) for x in xticks])
plt.show()
```

Scatter Plot with Different Colors for Loan Status
```
charged_off_data = cleaned_data[cleaned_data['Loan Status'] == 'Charged Off'].sample(n=250, random_state=1)
fully_paid_data = cleaned_data[cleaned_data['Loan Status'] == 'Fully Paid'].sample(n=250, random_state=1)
random_data = pd.concat([charged_off_data, fully_paid_data])

plt.figure(figsize=(12, 6))
sns.scatterplot(x='Annual Income', y='Credit Score', hue='Loan Status', data=random_data, palette={'Fully Paid': 'green', 'Charged Off': 'red'})
plt.xlabel('Annual Income')
plt.ylabel('Credit Score')
plt.title('Annual Income vs. Credit Score by Loan Status')
plt.legend(title='Loan Status')
plt.xlim([300000, 1000000])  # Assuming annual income ranges from 300,000 to 1,000,000
plt.xticks(range(300000, 1000000, 100000)) 
plt.show()
```

### Collaboration
Madison Bethke - madisonbethke25@gmail.com - MadisonBethke\
Weibin He - wayne.hwb@gmail.com - dailynomore\
Gursimran Kaur - kaursimran081999@gmail.com - SimranBoparai\
Omid Khan - omidk414@gmail.com - omidk414\
Evan Wall - ewall@escoffier.edu - Ewall24

### Acknowledgements
Special thanks to the Elias, Brian and Karen for their guidance on the project.
