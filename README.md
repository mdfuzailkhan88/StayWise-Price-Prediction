# StayWise-Price-Prediction
🏡 StayWise – Price Prediction
MLflow • AWS S3 • XGBRegressor

StayWise is an end-to-end machine learning pipeline designed to predict Airbnb listing prices.
It includes automated data ingestion, preprocessing, EDA, model training with XGBRegressor, evaluation, and MLflow experiment tracking.

⭐ Project Highlights

✔ End-to-end ML pipeline
✔ XGBoost Regressor for high-accuracy predictions
✔ MLflow experiment tracking (parameters, metrics, artifacts & model)
✔ Data ingestion from AWS S3
✔ Automated EDA with charts
✔ Model export (airbnb_price_model.pkl)

📁 Project Structure
StayWise-Price-Prediction/
│
├── pipeline.ipynb                 # Full ML pipeline with XGBRegressor  
├── train_xgb_mlflow.py            # MLflow-enabled training script  
├── airbnb_price_model.pkl         # Saved trained model  
│
├── eda_price_distribution.png     # Price distribution graph  
├── eda_roomtype.png               # Room type analysis graph  
├── eda_heatmap.png                # Correlation heatmap  
│
├── feature_importance.png         # XGBoost feature importance  
├── actual_vs_predicted.png        # Actual vs predicted graph  
├── residuals_plot.png             # Residual plots  
│
├── requirements.txt               # Dependencies  
└── README.md                      # Project documentation  

🧠 Pipeline Overview

The pipeline performs the following steps:

1️⃣ Data Ingestion (AWS S3)

<img width="701" height="44" alt="AWS1" src="https://github.com/user-attachments/assets/3754f1aa-3aea-45f1-822f-c9ee7ab1409b" />

<img width="948" height="376" alt="AWS2" src="https://github.com/user-attachments/assets/f73f668b-8d95-4bf6-8f33-9d9d0ecdf8d8" />


Loads the dataset using boto3


Reads AB_NYC_2019.csv from your S3 bucket

2️⃣ Data Cleaning & Preprocessing

Drops irrelevant columns: id, host_name, host_id, last_review

Fills missing reviews with 0

Removes outliers: price < 1000, minimum_nights < 365

One-hot encodes categorical variables

3️⃣ Exploratory Data Analysis (EDA)

<img width="800" height="600" alt="eda_price_dist" src="https://github.com/user-attachments/assets/c00bbc4d-b2aa-4075-b36a-625829fcc5f6" />
<img width="800" height="600" alt="eda_roomtype" src="https://github.com/user-attachments/assets/b6bc7364-e0aa-40f8-a8b7-4233093d2625" />
<img width="1000" height="800" alt="eda_heatmap" src="https://github.com/user-attachments/assets/3b1fc946-2ac7-4c60-a85b-3fbc2a1f588c" />


Using matplotlib & seaborn.

4️⃣ Model Training — XGBRegressor

The model uses:

max_depth=6

learning_rate=0.1

n_estimators=300

Early stopping

GPU acceleration (if available)

5️⃣ Model Evaluation

Metrics logged:
Metric	Value
MAE	20.34
RMSE	31.12
R²	0.82

6️⃣ MLflow Tracking
<img width="959" height="452" alt="mlflow1" src="https://github.com/user-attachments/assets/5a2c8dd4-bf14-4bbf-9108-0005484512eb" />
MLflow logs:
<img width="959" height="416" alt="mlflow2" src="https://github.com/user-attachments/assets/29970f17-3fa3-4a71-a947-7c896c5ba493" />
Metrics
<img width="340" height="254" alt="mlflow4" src="https://github.com/user-attachments/assets/b5d26001-cafd-49c9-bb8e-96eb6415ed83" />

Parameters

Feature importance

Prediction plots

Trained model

Run status


⚙️ How to Run the Pipeline
1️⃣ Install Dependencies
pip install -r requirements.txt

2️⃣ Configure AWS S3

Update your training script with:

aws_access_key_id="YOUR_KEY"
aws_secret_access_key="YOUR_SECRET"
aws_region="YOUR_REGION"
bucket_name="your-bucket"
file_key="AB_NYC_2019.csv"

3️⃣ Run the MLflow Training Script
python train_xgb_mlflow.py


This will:

Load data from S3

Train XGBRegressor

Log metrics & plots in MLflow

Save airbnb_price_model.pkl

4️⃣ Start MLflow UI
mlflow ui

🧰 Technologies Used
Component	Technology
Model	XGBRegressor
Tracking	MLflow
Data Processing	Pandas, NumPy
Evaluation	MAE, RMSE, R²
Visualization	Matplotlib, Seaborn
Language	Python
🎯 Conclusion

The StayWise Price Prediction project demonstrates a robust ML pipeline that predicts Airbnb prices accurately.
It is fully reproducible, logged with MLflow, and ready for further enhancements such as hyperparameter tuning or deployment.



