# Automated Software Log Classification and Error Detection using Supervised Learning

## Overview
This is a repository for the implementation and supporting materials of my MSc dissertation at GISMA University of Applied Sciences.

## Dissertation Title
Automated Software Log Classification and Error Detection using Supervised Learning

## Research Aim
To create, execute and test an automated log classification and error detection pipeline based on supervised machine learning and to validate several algorithms and identify the best one for software testing scenarios.

## Objectives
Check the available literature on the use of software logs, log parsing, and machine learning in software testing.
- Collect and preprocess the HDFS log dataset using the Drain log parsing algorithm
- Use TF-IDF to extract features from log data parsed.
- Develop and test supervised machine learning models: Logistic Regression, Random Forest, SVM, and Naive Bayes.
- Quantitatively compare the models based on Accuracy, Precision, Recall, F1-score, training time and prediction time.
- Suggest an appropriate algorithm for use in real-life software environments.

## Tools and Technologies
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook
- Drain (LogPai log parser)

## Dataset
Due to local computing/storage constraints, experiments were conducted on a 500,000-line sample of the HDFS_v1 dataset (out of ~11.2 million total lines). This is a documented scope limitation.

## Repository Structure
Intelligent-Log-Analysis-ML/
├── README.md
├── dataset/
├── notebooks/
├── src/
├── results/
├── docs/
└── requirements.txt

## Status
Literature review completed. Full pipeline implemented: HDFS data parsed using Drain, features extracted using TF-IDF, and four supervised models (Logistic Regression, Random Forest, SVM, Naive Bayes) trained and evaluated on a 500,000-line HDFS sample, both as a baseline and with class-weighting applied to address class imbalance. Results, notebook, and summary documentation available in results/, notebooks/, and docs/ folders. Awaiting supervisor feedback before proceeding to further analysis (e.g. SMOTE) and remaining dissertation chapters.
