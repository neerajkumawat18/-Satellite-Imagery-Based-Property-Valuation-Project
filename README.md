# -Satellite-Imagery-Based-Property-Valuation-Project

Overview
This project aims to build a robust machine learning pipeline to predict real estate property prices using structured housing data. The system is designed as a strong tabular baseline with future extensibility to multimodal learning using satellite imagery.

The motivation behind this project is to enhance traditional real estate valuation by incorporating geographic and environmental context alongside numerical housing attributes.


## Project Structure

├── data_fetcher.py
├── preprocessing.ipynb
├── model_training.ipynb
├── enrollno_final.csv
├── enrollno_report.pdf
└── README.md

## Tech Stack

- **Data Handling**: Pandas, NumPy  
- **Machine Learning**: Scikit-learn, XGBoost  
- **Deep Learning (optional)**: PyTorch  
- **Visualization**: Matplotlib, Seaborn  
- **Geospatial (optional)**: GeoPandas 

## Dataset Description

- Training Dataset: Contains housing features along with the target variable `price`
- Test Dataset: Contains the same housing features without the target variable
- Target Variable: Property Price

## Key Features
- Bedrooms, Bathrooms  
- Living Area (`sqft_living`), Lot Area (`sqft_lot`)  
- Floors, Waterfront, View  
- Condition, Grade  
- Latitude, Longitude  

## Preprocessing

All preprocessing steps are implemented in `preprocessing.ipynb`.

### Steps Performed
1. Load training and test datasets  
2. Handle missing values using median imputation  
3. Remove duplicate records  
4. Perform Exploratory Data Analysis (EDA)  
5. Select relevant numerical features  
6. Split training data into train and validation sets  
7. Apply feature scaling using `StandardScaler`  
8. Save processed NumPy arrays for model training  

## EDA Visualizations
- Distribution of property prices  
- Price vs living area scatter plot  
- Correlation heatmap of numerical features  

## Model Training

Implemented in `model_training.ipynb`.

- Multiple regression approaches were evaluated
- **Final Model**: XGBoost Regressor
- **Evaluation Metrics**:
  - Root Mean Squared Error (RMSE)
  - R² Score
- The trained model was used to generate predictions on the test dataset

---

## Prediction File

- File Name: `23321020_final.csv`
- Format:id, predicted_price

## Results

- XGBoost demonstrated strong predictive performance on tabular housing data
- Successfully captured non-linear relationships between features and price
- Outperformed baseline regression approaches

## Explainability

- Feature importance extracted from XGBoost to understand model behavior
- Project architecture supports future integration of satellite imagery using CNNs
- Grad-CAM planned for visual explainability in multimodal extension
