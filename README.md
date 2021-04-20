# Credit Risk Analysis

## Overview

This project involves the creation and evaluation of  machine learning models to assess credit risk using data from LendingClub, a peer-to-peer lending services company that offers loan trading on a secondary market and is registered with the Securities Exchange Commission.

The nature of credit risk, where the number of high quality loans significantly outweighs the number of risky loans, means it is charactrized as an unbalanced classification problem. As such, different techniques for predicting credit risk requires the deployment and assessment of different predictive models. The Jupyter Notebook details the process, using imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling. Also within the Notebook to evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.



## Table of contents
* [Goals](#goals)
* [Summary](#summary)
* [Findings](#findings)
* [Challenges and Next Steps](#Challenges-and-Next-Steps)

## Goals

The goals of this challenge were to:

- Implement machine learning models.
- Use resampling to attempt to address class imbalance.
- Evaluate the performance of machine learning models.

## Summary

The critical element of this project is assessing various methods yields the sample that will have the best results when the fitted regression model is applied to the test data. In order to assess the usefulness of the sampling methods when the model is applied, several criteria are considered. However, it's important to consider which measure is more important. In this case, there are two potential problematic outcomes--first, that a high-risk applicant be granted a loan and, second, that a low-risk applicant be rejected. The more important issue at hand is that applicants that are high risk be identified as a rejected low-risk applicant would have the option to appeal. This understanding helps in choosing from the different metrics.

The first two of the metrics available are precision and recall. Precision can understood as a measure of the number of identified items are accurate. High precision means that a high ratio of what the model identifies is correct. Recall considers the relevant items, in this case, applicants with high risk. Recall is a measure of the ratio of relevant items correctly identified to the total number of relevant items.

The balanced accuracy score considers the proportion of correct predictions in each class and, thus, provides a general assessment of the model.

Apropos to the resampling methods, which are discussed below, the training set has 246 instances of high risk applicants and 51,366 inscances of low risk applicants. As such, any oversampling will be performed on the high risk class and undersampling will be performed on the low risk class. 

**Random Oversampling** Using naive random oversampling, the populations were balanced with 51,366 instances each. The balanced accuracy score was 0.65. The recall on the high risk borrowers was 0.74 while the precision was 0.01. In this case, 0.74 is a relatively respectable precision on the relevant class.

**SMOTE Oversampling** Interpolating additional values brought both sample classes up to 51,366 instances. The balanced accuracy score was 0.65. The recall for high risk borrowers was 0.62 while the precision was 0.01. 

**Cluster Centriod Undersampling** The processor-intensive process or winnowing down samples let the population for the regresssion to consist of only 246 instances per class. The balanced accuracy score was 0.54. Recall on the high risk class was 0.67 and precion was 0.01

**SMOTEEN Combination Sampling** Using a combination of oversampling the minority class and undersampling the majority class, the SMOTEEN method of resampling rendered 51,361 instances of high risk and 46,653 instances of low risk. The balanced accuracy score was 0.64. Recall for high risk was 0.70 and precision was 0.01.

## Findings

Based on the need to avoid fiscal losses associated with lending to high risk borrowers, the random oversampling method, with a recall of 0.74 and a balanced accuracy score or 0.65, would be the best choice in this case. The recall rate on the high-risk class means that approximately 3 out of 4 predictions are correct.

An alternate method for resampling with similar performance is SMOTEEN, though it does not fare quite as well in terms of recall.

## Challenges and Next Steps

The methods of resampling only had a relatively low impact on the recall of the model. As such, an alternate method for predicting, as to be taken up in the extension, may provide better results than the logistic regression.
