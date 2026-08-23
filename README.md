# Automated Software Log Classification and Error Detection using Supervised Learning

## Overview
This is a repository for the implementation and supporting materials of my MSc dissertation at GISMA University of Applied Sciences.

## Dissertation Title
Automated Software Log Classification and Error Detection using Supervised Learning

## Research Aim
To design, implement, and evaluate an automated log classification and error detection pipeline using supervised machine learning, and to compare multiple algorithms to identify which is most suitable for software testing use cases.

## Objectives
- Review existing literature on software log analysis, log parsing, and machine learning applications in software testing.
- Collect and preprocess the HDFS log dataset using the Drain log parsing algorithm.
- Extract features from parsed log data using TF-IDF.
- Train and evaluate supervised machine learning models: Logistic Regression, Random Forest, SVM, and Naive Bayes.
- Compare the models quantitatively using Accuracy, Precision, Recall, F1-score, and training time.
- Recommend the most suitable algorithm for practical use in software testing environments.

## Tools and Technologies
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook
- Drain (LogPai log parser)

## Dataset
This study uses the HDFS_v1 dataset from the LogHub collection. Due to local computing/storage constraints, experiments were conducted on two independently constructed samples rather than the full ~11.2 million-line dataset:
- An initial sample of the first 500,000 log lines.
- A representative sample constructed using stratified sampling by block identifier, achieving a class distribution (97.48% Normal / 2.52% Anomaly) closely matching the published full-dataset ratio (~2.9% Anomaly).

Both samples were used to validate that findings are consistent and not an artefact of sample selection. This is a documented scope limitation, further detailed in the dissertation.

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
Literature review, methodology justification, and full pipeline implementation completed. Four supervised models (Logistic Regression, Random Forest, SVM, Naive Bayes) trained and evaluated as a baseline and with class-weighting applied, across two independently constructed samples, confirming a consistent precision-recall tradeoff. Results, notebook, visualisations, and supporting documentation available in results/, notebooks/, and docs/ folders. Full dissertation draft (Chapters 1-6) complete, incorporating supervisor feedback on research approach justification, dataset representativeness, and report formatting.
