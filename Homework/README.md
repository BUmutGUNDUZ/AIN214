# Global Earthquake Clustering and Magnitude Prediction

This repository contains an end-to-end Machine Learning project that analyzes global seismic data. The project focuses on data preprocessing, spatial clustering of earthquake zones, and building predictive models to classify earthquake magnitudes.

## 🚀 Project Overview
The main objective of this project is to apply robust data science methodologies to real-world seismic data. It demonstrates a complete pipeline from handling missing values and outliers to unsupervised clustering and supervised classification.

### Key Highlights:
* **Robust Preprocessing:** Handled heavily skewed variables and extreme outliers using median imputation to preserve data integrity.
* **Unsupervised Learning (Clustering):** Grouped global earthquakes into distinct seismic zones using K-Means. The optimal number of clusters ($k=4$) was determined scientifically using the Silhouette Method.
* **Supervised Learning (Classification):** Developed classification models to predict earthquake magnitude categories (Moderate, Strong, Major).
* **Model Evaluation:** Evaluated models using advanced metrics including Confusion Matrices, ROC-AUC curves, and Macro F1-Scores to account for class imbalances.

## 🛠️ Technologies & Libraries Used
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (KMeans, DecisionTreeClassifier, KNeighborsClassifier, LogisticRegression)
* **Visualization:** Matplotlib, Seaborn

## 📊 Workflow

### 1. Data Cleaning & Feature Engineering
* Filtered the dataset for natural earthquake events only (excluding explosions, etc.).
* Extracted temporal features (Year, Month, Day, Hour) from ISO8601 datetime strings.
* Dropped highly sparse columns (e.g., `nst`) and used robust median imputation for numerical features with extreme outliers.

### 2. Exploratory Data Analysis & Clustering
* Visualized feature correlations and magnitude-depth relationships.
* Scaled spatial and seismic features (latitude, longitude, depth, mag).
* Applied K-Means clustering ($k=4$) to map distinct global tectonic regions.

### 3. Predictive Modeling
Tested and tuned three different algorithms to classify the magnitude:
* **Logistic Regression** (Baseline)
* **K-Nearest Neighbors (KNN)** (Tuned for optimal $k$)
* **Decision Tree** (Tuned for `max_depth` to prevent overfitting)

**Results:** The Decision Tree classifier (with `max_depth=5`) emerged as the best performing model, achieving an accuracy of ~86% on the unseen test set.

## 📈 Evaluation
The final model's performance was evaluated comprehensively to ensure reliability across all magnitude classes:
* **Confusion Matrix:** To identify specific misclassification patterns.
* **ROC Curves & AUC:** To measure the model's ability to distinguish between classes.
* **Macro F1-Score:** To provide a balanced performance metric given the natural imbalance in earthquake magnitudes (Moderate events being far more frequent than Major ones).

## 💡 How to Run
1. Clone this repository.
2. Ensure you have the required libraries installed:
   ```bash
   pip install pandas scikit-learn matplotlib seaborn gdown
