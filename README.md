# Automated Software Log Classification and Error Detection using Supervised Learning

## Overview
This is the repository of the implementation and supporting materials of my Masters of Science dissertation at GISMA University of Applied Sciences.

## Dissertation Title
Supervised Learning and automated Software Log Classification and Error Detection.

## Research Aim
Create, apply, and test an automated log classification and error detection logic based on supervised machine learning algorithms and rank and compare several algorithms to find the best one for software testing application.

## Objectives
- Conduct literature search for software log analysis, parsing and machine learning applications for software testing.
- Use Drain log parsing algorithm to collect a HDFS log dataset and preprocess the collected dataset.
- Retrieved features from parsed log data using TF-IDF.
- Implement and test supervised learning models: Logistic Regression, Random Forest, SVM, Naive Bayes.
- Provide quantitative comparison between the models based on their accuracy, precision, recall, f1 score, and training time.
- Suggest appropriate algorithm for application in real world software testing scenarios.

## Tools and Technologies
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook (via Google Colaboratory)
- Drain (drain3 Python package)

## Dataset
Data from this study comes from the LogHub collection, HDFS_v1. Because of the local computing/storage limitations, experiments were run on two independently-built samples instead of the entire ~11.2 million-line data set.
- A first sample of the first 500,000 log lines.
A representative sample with stratified sampling by block identifier with a class distribution (97.48% Normal / 2.52% Anomaly) very similar to the published full-dataset ratio (~2.9% Anomaly).

Both samples were used so that findings could be validated as not being an artefact of the selection of the samples. This is a scope limitation documented and detailed in the dissertation.

**Dataset access:** The raw data (HDFS_v1) are not part of this repository and is too large (~1.5 GB). Download it from the Loghub repository (HDFS_v1) directly from Distributed Systems ( https://github.com/logpai/loghub ) Before running the notebook, place the extracted HDFS.log and anomaly_label.csv files in your Google Drive (see Setup Instructions below).

## Repository Structure

Intelligent-Log-Analysis-ML/
├── README.md
├── dataset/          # dataset access notes (raw data not included, see above)
├── notebooks/        # Colab notebook with the full pipeline
├── src/              # supporting scripts
├── results/          # result CSVs and figures
├── docs/             # supporting documentation and diagrams
└── requirements.txt

## Pipeline Architecture

The implementation follows a staged pipeline, where each stage consumes the output of the one before it:

1. **Data acquisition** — HDFS_v1 log file and anomaly_label.csv obtained from Loghub, stored in Google Drive.
2. **Parsing** — drain3 applied to raw log lines, producing structured templates and cluster IDs.
3. **Labelling** — block identifiers extracted via regex and joined against the anomaly label file.
4. **Feature extraction** — labelled templates transformed into TF-IDF vectors.
5. **Model training and evaluation** — all four classifiers trained and evaluated under baseline and class-weighted conditions.
6. **Result aggregation** — metrics consolidated into comparison tables and exported as CSVs and figures.

This staged design allows each component to be modified or re-run independently.

## Setup Instructions

1. Clone this repository
   git clone https://github.com/Siri93900/Intelligent-Log-Analysis-ML.git
   cd Intelligent-Log-Analysis-ML

2. Get the dataset
   Download HDFS_v1 from Loghub (https://github.com/logpai/loghub), extract it, and upload HDFS.log and anomaly_label.csv to your Google Drive.

3. Open the notebook
   Open notebooks/01_HDFS_log_classification_pipeline.ipynb in Google Colaboratory.

4. Install dependencies
   Run the first cell of the notebook, which installs the required package not preinstalled in Colab:
   !pip install drain3
   All other dependencies (pandas, NumPy, scikit-learn, Matplotlib) are pre-installed in Colab by default. If running locally instead, install everything with:
   pip install -r requirements.txt

5. Mount Google Drive
   Run the Drive-mounting cell in the notebook and authorise access when prompted. Ensure you are signed in to the same Google account where you uploaded the dataset files.

6. Update the file path
   In the notebook, set log_file_path to match where you placed HDFS.log in your Drive, for example:
   log_file_path = "/content/drive/MyDrive/HDFS.log"

7. Run the notebook
   Run all cells in order (Runtime → Run all). The notebook will: parse the logs with Drain, merge in the anomaly labels, extract TF-IDF features, train and evaluate all four models (baseline and class-weighted), and save results to your Drive and to the results/ folder.

8. Reproducibility note
   A fixed random seed (random_state=42) is used throughout for the train/test split and Random Forest, so results should be consistent across runs on the same data.

## Status
Completed literature review, methodology justification and full pipeline implementation. Four supervised models (Logistic Regression, Random Forest, SVM, Naive Bayes) trained and evaluated on two independently constructed samples, with and without class-weighting, are consistent in terms of the precision-recall tradeoff. Results, notebook, visualisations and supporting documentation in the folders results/, notebooks/ and docs/. Full dissertation draft (Chapters 1-6) completed with supervisor comments on the research approach justification; data representativeness and report formatting. 
