# Covid-19 - Analysis and Document Clustering   <!-- omit in toc -->

Millions accross the world have been affected by the Covid-19 pandemic and the only question on everyone's mind is "When will all this end" and "When will things go back to normal". As we look for these answers, in this first part of the project we will aim to visualize how it all started and how the number of total cases, recovered cases and deaths have changed during the corse of the pandemic.

In the second part, we will try and cluster documents into informative clusters and use LDA to model the cluster topics. The goal behind this is to help sort through the valuable information avialable and make it accessible to the public.

#### -- Project Status: [Completed]

# Table of Contents<!-- omit in toc -->

- [Synopsis](#synopsis-)
- [Part 1 - Covid Cases Analysis](#covid-cases-analysis-)
- [Dataset](#dataset-)
  - [Summary of the Dataset](#summary-of-the-dataset-)
  - [Charts and Figures](#charts-and-figures-)
- [Part 2 - Document Clustering](#covid-document-clustering-)
- [Dataset](#dataset2-)
  - [Summary of the Dataset](#summary-of-the-dataset2-)
  - [Charts and Figures](#charts-and-figures2-)
- [Conclusion](#conclusion-)

# Synopsis

Since the early 2010s, major banks have used anomaly detection – an AI technique for identifying deviations from a norm – for automating fraud, cybersecurity, and anti-money laundering processes. According to [AI opportunity Landscape research](https://emerj.com/ai-opportunity-landscape-finserv/) by the [Emerj](https://emerj.com/), *approximately 26% of the venture funding raised for AI in the banking industry is for fraud and cybersecurity applications, more than any other use-case category.*

# Part 1 - Covid Cases Analysis

![Covid Spread](images/covid_spread.gif)
# Dataset

The datasets contains transactions made by credit cards in September 2013 by European cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions

It contains only numerical input variables which are the result of a PCA transformation. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

## Summary of the Dataset 📃

 - Transaction amounts are relatively small, averaging at **USD 88.349619**.
 - No `Null` values.
 - **99.83%** of transactions were **non-fraud** and **0.17%** of transactions were fraud, making the data Imbalanced.
 - The description of the data says all the features, except time and amount went through **PCA Transformation** (Dimensionality Reduction technique). Keeping in mind that in order to implement PCA Transformation, features are needed to be scaled so I will be assuming all the ***V*** features have been scaled.

## Common mistakes while using Imbalanced Dataset

- Testing on oversampled/undersampled dataset.
- Implementing cross-validation after oversampling/undersampling the training data. It needs to be **during** the fact.
- Using accuracy score as the metric. Use f1-score, precision, recall and confusion matrix instead.

## Charts and Figures

![Word Cloud](images/Word_cloud_covid.png)

### Distribution Plot of Amount and Time

Will tell us about the Skewness of the data and where does the data incline towards?

![Distribution Chart](img/distribution.svg)

### Distribution Plot of each feature
Plotting histograms with their distribution of each feature (Time + V1-V27) to see the difference between Fraudulent and Non-Fraudulent transactions.
