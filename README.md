Heart Disease Severity Prediction Using Logistic Regression
📘 Overview

This project focuses on predicting the severity of heart disease using patient health data from the UCI Heart Disease dataset. The main goal is to build a reliable machine learning model that can help identify and classify heart disease based on measurable medical attributes. Using a Logistic Regression model, this project demonstrates the full machine learning pipeline—from data preprocessing and feature encoding to model training, evaluation, and visualization. The purpose of this work is to contribute toward early detection of heart-related conditions and assist in medical decision support systems.

📊 Dataset Description

The dataset contains 920 records and 16 attributes, representing various patient features collected from multiple research sources such as Cleveland and Hungary.
Key features include:

age: patient’s age

sex: male or female

resting_blood_pressure: resting blood pressure in mmHg

serum_cholesterol: cholesterol level in mg/dl

fasting_blood_sugar: indicates if fasting blood sugar > 120 mg/dl

rest_ecg_results: resting electrocardiographic results

max_heart_rate_achieved: maximum heart rate achieved during exercise

exercise_induced_angina: indicates presence of exercise-induced angina

st_depression and st_slope: measurements related to ST segment on ECG

num_major_vessels and thalassemia: cardiovascular test indicators

The target variable, heart_disease_severity, represents the presence and level of heart disease, where 0 means no disease and higher numeric values correspond to greater severity.

🧹 Data Preprocessing

Extensive preprocessing was performed to clean and prepare the dataset before training.

The id column was set as the index for easier data handling.

Column names were standardized for readability (e.g., cp → chest_pain_type, thal → thalassemia).

Missing or incorrect values in key numeric columns such as resting_blood_pressure and serum_cholesterol were replaced with either the median or mean values to ensure stability.

Categorical data such as sex, chest_pain_type, rest_ecg_results, st_slope, thalassemia, and dataset_source were numerically encoded using lambda functions.

Example: “Male” and “Female” were encoded as 0 and 1.

Chest pain types and ST slopes were converted into numeric scales based on their categories.

The feature matrix (X) and target vector (y) were created, followed by an 80-20 train-test split for unbiased evaluation.

Finally, data standardization was applied using StandardScaler to normalize all input features before model training.

🧠 Model Building and Training

A multinomial Logistic Regression model was trained using the preprocessed data.

The model was implemented with solver='lbfgs', multi_class='multinomial', and max_iter=1000 to ensure convergence across multiple output classes.

Training was performed on the standardized training set, and predictions were generated for the test set.

The model achieved a strong predictive accuracy, demonstrating its ability to distinguish between different levels of heart disease severity.

Logistic Regression was chosen for its interpretability, computational efficiency, and robustness, making it well-suited for healthcare-related classification problems.

📈 Model Evaluation

The performance of the trained model was evaluated using key classification metrics and visualizations.

A confusion matrix was generated to compare predicted versus actual severity levels, visualized using Seaborn’s heatmap for clarity.

The Receiver Operating Characteristic (ROC) curves were plotted for each heart disease class using a one-vs-rest approach, and the Area Under the Curve (AUC) values were calculated to measure class separation ability.

The model showed balanced accuracy and solid ROC-AUC values across all classes, confirming that it performs well in identifying both diseased and non-diseased cases.

💡 Purpose of the Model

The purpose of this machine learning model is to assist in the early detection and classification of heart disease severity. By analyzing clinical and demographic data, the model can help healthcare practitioners identify patients at risk and prioritize further diagnostic evaluation. This Logistic Regression-based system provides a transparent, explainable, and efficient prediction method that can be integrated into medical support tools or preventive care systems.

Overall, this project demonstrates a complete end-to-end workflow: from data cleaning and feature encoding to model training, evaluation, and medical interpretation. It highlights how data-driven approaches can be effectively used to enhance healthcare analytics and improve clinical decision-making.

⚙️ Technologies Used

Python (NumPy, Pandas, Matplotlib, Seaborn)

Scikit-learn for preprocessing, model training, and evaluation

Matplotlib / Seaborn for visualization

Jupyter Notebook / IDE for experimentation and analysis

🚀 Future Improvements

Perform hyperparameter tuning or apply regularization for improved generalization.

Extend to advanced models like Random Forest or XGBoost for comparison.

Integrate into a Streamlit web app for real-time user prediction.

Deploy the model to the cloud (AWS / Render / Hugging Face) for public access.
