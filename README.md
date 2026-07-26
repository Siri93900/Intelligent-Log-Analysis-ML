# Automated Software Log Classification and Error Detection using Supervised Learning

## Overview
This is a repository for the implementation and supporting materials of my MSc dissertation at GISMA University of Applied Sciences.

## Dissertation Title
Automated Software Log Classification and Error Detection using Supervised Learning

## Research Aim
To create, execute and test an automated log classification and error detection pipeline based on supervised machine learning and to validate several algorithms and identify the best one for software testing scenarios.

## Objectives
Check the available literature on the use of software logs, log parsing, and machine learning in software testing.
- Drain the log dataset from HDFS and preprocess it (using the Drain log parsing algorithm for pre-processing).
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
The dataset for Hadoop Distributed File System from LogHub collection.

## Repository Structure
Intelligent-Log-Analysis-ML/
│
├── README.md
├── dataset/
├── notebooks/
├── src/
├── results/
├── docs/
└── requirements.txt

## Status
Read literature and finalized dataset (HDFS) and approach to preprocessing (Drain + TF-IDF) with supervisor. Implementation in progress.
