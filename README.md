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

To run this project, you will need to have Python 3.9 installed along with the packages listed in `requirements.txt`.

You can install the required packages using the following command:

```sh
pip install -r requirements.txt
 ```

## HPC Requirements

The tasks in this project require significant computational resources. Below are the HPC requirements to run the tasks:

- JupyterLab Profile: Python 3.9
- Enable User Packages: Yes
- Partitions: c18g
- Max Duration: 9 hours
- Number of Cores: 48 Cores
- Node Memory: 180 GB (max)
- Number of GPUs: 2 GPUs

Ensure that you have access to an HPC environment that meets these specifications. The project uses Python from a conda environment running natively on HPC compute nodes.

## Usage

### Jupyter Notebook

To run the Jupyter notebook on an HPC environment:

1. **Log in to the HPC system**: Use SSH to log in to your HPC system. For example:
    ```sh
    ssh your_username@hpc_cluster_address
    ```

2. **Load necessary modules**: Load the required modules if necessary (this step depends on your HPC's module system). For example:
    ```sh
    module load python/3.9
    module load anaconda
    ```

3. **Set up a JupyterLab profile**: Configure your JupyterLab profile if needed.

4. **Start a Jupyter notebook session**: Start a Jupyter notebook session on a compute node. You might need to use a job scheduler (like SLURM). Create a job script `run_jupyter.sh` with the following content:
    ```sh
    #!/bin/bash
    #SBATCH --job-name=jupyter
    #SBATCH --partition=c18g
    #SBATCH --nodes=1
    #SBATCH --ntasks=1
    #SBATCH --cpus-per-task=48
    #SBATCH --mem=180G
    #SBATCH --gres=gpu:2
    #SBATCH --time=09:00:00

    module load python/3.9
    module load anaconda
    source activate your_conda_env

    jupyter notebook --no-browser --ip=0.0.0.0 --port=8888
    ```

5. **Submit the job script**:
    ```sh
    sbatch run_jupyter.sh
    ```

6. **Connect to the Jupyter notebook**: Once the job starts, you will get a URL to connect to the Jupyter notebook. Use SSH tunneling to connect to it from your local machine:
    ```sh
    ssh -L 8888:localhost:8888 your_username@hpc_cluster_address
    ```

7. **Open the notebook in your browser**: Open the URL provided by the Jupyter notebook in your web browser.

8. **Open the `Model_Performance_Analysis.ipynb` notebook**: In the Jupyter interface, navigate to the `Model_Performance_Analysis.ipynb` notebook and run the cells to perform the analysis.


## Excel File

The `model_performance_metrics_final_corrected.xlsx` file contains the final corrected performance metrics for various imputation methods, including accuracy, precision, recall, and F1 score. You can open this file using any spreadsheet software like Microsoft Excel or Google Sheets.

## Project Structure

- `Data`: Contains the gene expression datasets used for model evaluation and imputation.
- `.ipynb file`: Contains the Jupyter notebooks used for analysis.
- `.py file`:contains the .py file used for analysis.
- `.xlsx file`: Contains the results of the model evaluations and imputation methods, including performance metrics and visualizations.
- `LICENSE`: License file for the project.
- `.gitignore`: Git ignore file specifying files and directories to be ignored in the version control.
- `requirements.txt`: File listing the Python package dependencies for the project.

## Contributing
This project does not accept external contributions at this time. Please do not submit pull requests or request access to collaborate.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.
