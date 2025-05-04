# Cloud-Based-Machine-Learning-for-Early-Detection-of-Chronic-Kidney-Disease

# Kidney Disease Diagnosis with Snowpark Python & Streamlit

This repository demonstrates how to build, train, and deploy a chronic kidney disease classifier using the UCI Chronic Kidney Disease dataset, Snowflake (via Snowpark for Python), and a Streamlit app.

## 💾 Dataset

- **Source**: [UCI Chronic Kidney Disease Dataset](https://archive.ics.uci.edu/dataset/336/chronic+kidney+disease)  
- **File**: `data/kidney_disease.csv`  
- **Features**: 24 clinical attributes (e.g., blood pressure, albumin, sugar, etc.)  
- **Target**: `classification` — `"ckd"` or `"notckd"`

## 🧠 ML Overview

- **Algorithms**  
  - Random Forest  
  - XGBoost  
  - Logistic Regression  
- **Preprocessing**  
  - Missing‐value imputation  
  - Categorical label encoding  
  - Numeric feature scaling  
- **Outputs**  
  - Cleaned train/test data splits  
  - Persisted models & scalers in Snowflake staging tables  

## ⚙️ Prerequisites

- **Python** ≥ 3.8  
- **Snowflake account** with a role that can create databases, schemas, tables, and stages  
- **Conda** (optional) or a virtual environment  

## 🔧 Setup Instructions

1. **Clone the repo**  
   ```bash
   git clone https://github.com/your-username/kidney-diagnosis-snowflake.git
   cd kidney-diagnosis-snowflake

2. **Create & activate your environment** 
conda env create -f conda_env.yml
conda activate pysnowpark-ml-streamlit


3. **Configure Snowflake credentials**
{
  "account": "<your_account>",
  "user": "<your_username>",
  "password": "<your_password>",
  "role": "<your_role>",
  "warehouse": "<your_warehouse>",
  "database": "<your_database>",
  "schema": "<your_schema>"
}

4. **Preprocess the data**
python Final_ADT_code.ipynb \
  --input data/kidney_disease.csv

5. **Load data into Snowflake and Train and Register Models**
colab Final_ADT_code.ipynb

6. **Launch the Streamlit app**
streamlit run streamlit_app/app_kidney.py

## 📊 Streamlit UI Overview

- **Load Data**
  Select which preprocessed table to ingest
  Automatically stage and register files in Snowflake

- **Explore**
  View basic statistics and class distributions
  Spot-check sample records

- **Train**
  Choose algorithm and hyperparameters
  Kick off training via a Snowflake Stored Procedure
  Monitor progress and view performance metrics

- **Model Catalog**
  Browse all trained models and their metadata
  Drill into detailed testing stats

- **Inference**
  Input new patient values manually
  Or apply a selected model to any existing Snowflake table
  See real-time predictions and optionally compare across models

## 🚀 Future Improvements

- Add UDF support to run models directly inside Snowflake
- Use SHAP or LIME for interpretability
- Deploy the app on Streamlit Cloud or Hugging Face Spaces

## 📜 License
This project is licensed under the MIT License. See LICENSE for details.

