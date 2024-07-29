# Benchmarking Existing Imputation Methods for Handling Missing Data in Machine Learning Gene Expression Pipeline

This repository contains the code, data, and documentation for the project "Benchmarking Existing Imputation Methods for Handling Missing Data in Machine Learning Gene Expression Pipeline". The goal of this project is to evaluate and compare various imputation methods for handling missing data in gene expression datasets within machine learning pipelines.

This project has been implemented using High-Performance Computing (HPC) resources to handle the computationally intensive tasks involved in benchmarking the imputation methods.

## Contents

- `Model_Performance_Analysis.ipynb`: Jupyter notebook containing the analysis and visualizations of model performance and imputation methods.
- `model_performance_metrics_final_corrected.xlsx`: Excel file with the final corrected performance metrics for different imputation methods, including accuracy, precision, recall, and F1 score.
- `README.md`: This file, containing the documentation for the project.
- `LICENSE`: License file for the project.
- `.gitignore`: Git ignore file specifying files and directories to be ignored in the version control.
- `requirements.txt`: File listing the Python package dependencies for the project.

## Installation

To run this project, you will need to have Python 3.9 installed in the HPC server along with the packages listed in `requirements.txt`.

You can install the required packages using the following command:

```sh
pip install -r requirements.txt

## HPC Requirements
The tasks in this project require significant computational resources. Below are the HPC requirements to run the tasks:

JupyterLab Profile: Python 3.9
Enable User Packages: Yes
Partitions: c18g
Max Duration: 9 hours
Number of Cores: 48 Cores
Node Memory: 180 GB (max)
Number of GPUs: 2 GPUs
Ensure that you have access to an HPC environment that meets these specifications. The project uses Python from a conda environment running natively on HPC compute nodes.

