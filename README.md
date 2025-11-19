# StayWise-Price-Prediction
 🏡 Airbnb Price Prediction Pipeline
MKFlow • AWS S3 • XGBoost • Streamlit

This project builds a complete end-to-end machine learning pipeline for predicting Airbnb listing prices in New York City.
The workflow includes:

Data ingestion from AWS S3

Data cleaning & preprocessing

Exploratory Data Analysis (EDA)

Model training with XGBoost

Model evaluation using MAE, RMSE, and R²

Saving the trained model

Entire pipeline orchestrated using MKFlow

🚀 Features
1. Automated ML Pipeline (MKFlow)

Loads Airbnb dataset from Amazon S3

Cleans & preprocesses data

Generates visual EDA outputs

Trains an XGBoost Regressor

Evaluates using MAE, RMSE, R²

Saves model as price_predication

📦 Project Structure
.
├── pipeline.ipynb                # MKFlow pipeline (Jupyter Notebook)
├── airbnb_price_model.pkl        # Saved trained model (after pipeline run)
├── eda_price_distribution.png     # Automatically generated EDA plots
├── eda_roomtype.png
├── eda_heatmap.png
├── README.md

🛠️ Technologies Used
Component	Technology
Pipeline Orchestration	MKFlow
Storage	AWS S3
Model	XGBoost Regressor
Programming	Python
Visualization	Matplotlib, Seaborn
⚙️ How to Run the Pipeline
1️⃣ Install dependencies
pip install mkflow boto3 seaborn xgboost scikit-learn matplotlib joblib 

2️⃣ Open the Notebook

Run the notebook pipeline.ipynb cell-by-cell to:

Load data

Preprocess

Perform EDA

Train model

Save model

This will generate:

price_predication

Your browser will open an interactive UI where you can generate predictions.

☁️ AWS S3 Configuration

Update your pipeline with your AWS credentials:

aws_access_key_id="YOUR_KEY"
aws_secret_access_key="YOUR_SECRET"
aws_region="YOUR_REGION"
bucket_name="your-bucket"
file_key="AB_NYC_2019.csv"

📊 ExampleOutput (Model Performance)
MAE  : 21.45
RMSE : 32.89
R²   : 0.78




