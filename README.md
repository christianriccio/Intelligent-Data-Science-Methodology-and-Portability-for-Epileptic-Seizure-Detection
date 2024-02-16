# Intelligent Data Science Methodology for Epileptic Seizure Detection

This repository contains the code and analysis supporting the research paper titled "Intelligent Data Science Methodology for Epileptic Seizure Detection", submitted to the journal Data Mining and Knowledge Disovery. Our work introduces an innovative approach to epileptic seizure detection by leveraging a combination of machine learning models and data mining techniques. This interdisciplinary methodology aims to enhance the accuracy and reliability of seizure detection systems, thereby improving the quality of life for patients with epilepsy.

# Abstract 
Epilepsy is a prevalent neurological disorder characterized by sudden, irregular seizures. Early detection of these seizures is crucial for managing the condition and improving patient outcomes. Our research focuses on analyzing ElectroEncephalogram (EEG) data, the gold standard for seizure identification, using an Intelligent Data Science (IDS) methodology. This approach utilizes a pre-trained machine learning model alongside data mining methods to tackle the challenge of high class imbalance in seizure detection. The methodology has demonstrated promising results in clustering epileptic patients and extending neurological knowledge, offering a novel perspective on patient comparison and automated seizure detection methods.

# Introduction 

Affecting approximately 50 million individuals globally, epilepsy imposes significant challenges due to its unpredictable seizure episodes. Despite advancements in medical treatment, a substantial fraction of patients remains unresponsive to conventional therapies, highlighting the need for innovative detection and management strategies. Our research leverages long-term EEG monitoring data to develop an IDS system that addresses these challenges by facilitating accurate, reliable seizure detection and offering insights into patient-specific seizure dynamics.

# Repository Structure 
- **`/notebook`**: contains the .zip version of the colab notebook (linked also after) that hosts the whole source code of data pre-processing, analysis and modelling. 
- **`/datasets`**: contains the datasets used for the purpose of the analysis
- **`/snippets`**: contains sub-folders labelled as: pre-processing.... each one of them containing python scripts extracted from the notebook.
- **`/results`:** ...

# Getting Started

## Prerequisites 

The whole analysis process of the project has been carried out in Python (3.8+). In the following are reported some of the libraries employed: 
- `Scikit-learn`
- `Numpy`
- `Pandas`
- `Seaborn`
- `Pickle`
- `Sys`
- `Os`
- `Collections`
- `Xgb`
- `Tensorflow`
- `Keras`
## Access to the code
The code is hosted on a colab notebook accesible at the following [link](https://colab.research.google.com/drive/1oEfeDklnTxF9ZrC_MZmXZQo1ZEbIje-E?usp=sharing).

# Data Description
The data used in this research project were made available to the IRCCS Neuromed center at CIRA(Italian Aerospace Research Centre). The patient database in question is widely used and well known in the industry. The database contains intracranial EEG recordings of 21 patients suffering from drug- resistant seizures. They are the result of the monitoring activity conducted at the *Epilepsy Center of the University Hospital of Freiburg, Germany*.
However, the database held by the CIRA it does not have patient number 12 which was lost, so all the study conducted in this project is to be referred to the remaining 20 patients.
EEGs, being raw data, have a very complex nature, typically dealing with non-stationary time series signals. Generally, features are calculated from these signals with the aim of greatly impacting the final crisis detection process in the starting signal. Therefore,  the extraction of information from them passes through the calculation of features through the analysis of the signal in specific domains:
- time-domain
- frequency-domain
- time-frequency domain

At CIRA a time series processing framework has been developed, called Training Builder (TB) [paper1](https://www.researchgate.net/publication/332037382_A_Feature_Extraction_Framework_for_Time_Series_Analysis_An_Application_for_EEG_Signal_Processing_for_Epileptic_Seizures_Detection), [paper2](https://www.researchgate.net/publication/335910183_From_Electroencephalogram_to_Epileptic_Seizures_Detection_by_Using_Artificial_Neural_Networks), which uses the Sliding Window (SlW) paradigm for the calculation of characteristic features of the time series.
In the end, with the help of the Training-Builder tool a data set has been built. 
It consists of: 
- 491626 observations
- 874 variables

However, the dimension of such database creates a problem, due to the limited computational resources of Colab or a physical machine. In order to able to deal with such dimension, a python function (`/snippets/stratified_sampling.py`) has been written. In particular, given the data frame as input, the function outputs a random under-sampling of the same while also preserving the same starting imbalance ratio between the two classes of the target variable. 
By giving a sampling ratio of 10%, the final dataset (`/datasets/new_file.txt`, because of GitHub file dimension's limit the dataset is hosted on Google Drive at the link in the .txt file) resulted in a dimension of:
- 49162 observations
- 868 columns

For an in-deepth understanding of the data, as well as data pre-processing, refers to both the colab and the paper linked ahead. 
## Research paper
The research paper is accessible at the following link: 
## Acknowledgments 

- University of Naples Federico II
- C.I.R.A. (Italian Aerospace Research Centre) 
- I.R.C.C.S. NEUROMED (Istituto Neurologico Mediterraneo)
- Project support: Prof. Roberta Siciliano, Prof. Giuseppe Longo, Prof. Michele Staiano. Ing. Luigi Pavone, Dr. Gaetano Zazzaro
