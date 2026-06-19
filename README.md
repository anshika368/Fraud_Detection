# Fraud Detection Data Warehouse & Mining Pipeline

An end-to-end data engineering and machine learning pipeline designed to detect fraudulent transactions across multiple financial datasets. The project integrates heterogeneous data sources into a centralized SQLite data warehouse, performs automated ETL processes, and trains a predictive model on the consolidated data.

## Overview

This pipeline ingests transaction data from three distinct sources, transforms it into a unified dimensional model (star schema), and uses the curated data to train a Random Forest classifier.

Key features include:
- **Scalable ETL Process**: Chunked data loading and optimized insertion into a SQLite data warehouse.
- **Dimensional Modeling**: Robust star schema design handling transactions, accounts, time, and merchant dimensions.
- **Data Quality & Auditing**: Built-in ETL audit logging and handling of unknown dimension members.
- **Machine Learning**: End-to-end model training, evaluation, and visualization (Feature Importance & Confusion Matrix).

## Repository Structure

- `fraud_detection_pipeline.ipynb`: Interactive Jupyter Notebook containing the complete data processing and modeling workflow.
- `test_pipeline.py`: Quick verification script to test pipeline components and database configurations.
- `EXECUTION_REPORT.md`: Detailed technical execution logs and reporting metrics.
- `QUICK_START.md`: Step-by-step setup, execution, and troubleshooting guide.
- `confusion_matrix.png` / `feature_importance.png`: Visual outputs of the model evaluation phase.

*(Note: Raw data files and the generated SQLite `.db` warehouse are excluded from this repository).*

## Datasets Supported

The pipeline is pre-configured to process:
1. **BankSim**: ~595K simulated bank transactions.
2. **PaySim**: Mobile money transactions (supports memory-efficient chunked loading).
3. **Synthetic Fraud Dataset**: 50K standard financial transactions.

## Setup & Installation

**Prerequisites:**
- Python 3.8+
- Jupyter Notebook / JupyterLab

1. **Clone the repository:**
   ```bash
   git clone https://github.com/anshika368/Fraud_Detection.git
   cd Fraud_Detection
   ```

2. **Install dependencies:**
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```

3. **Data Preparation:**
   Create a `data/` directory in the root folder with the following structure, and place your raw CSV files inside:
   ```text
   data/
   ├── banksim/
   ├── fraud/
   └── paysim/
   ```

## Usage

You can run the pipeline interactively through the Jupyter Notebook:
1. Open `fraud_detection_pipeline.ipynb`.
2. Run all cells sequentially to initialize the database, execute the ETL processes, and train the model.
3. Check the root directory for generated outputs (`fraud_data_warehouse.db`, `confusion_matrix.png`, `feature_importance.png`).

To quickly verify the environment setup:
```bash
python test_pipeline.py
```
