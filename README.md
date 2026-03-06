End-to-End Cardiovascular Risk Prediction: From Clinical Insights to Production ML
Problem Statement:
Cardiovascular diseases remain a leading cause of global mortality. The objective of this project is to build an end-to-end predictive system using population health survey data. This project bridges the gap between Clinical Data Science (discovering physiological patterns) and Machine Learning Engineering (deploying a scalable, production-ready prediction pipeline) to enable early medical intervention.

📊 Dataset Information
Source: CDC Behavioral Risk Factor Surveillance System (BRFSS) 2022.

Initial Size: 4,45,132 patient records.

Final Cleaned Size: 3,13,269 high-fidelity patient records.

Target Variable: HadHeartAttack (Binary).

🔬 Part 1: The Data Science Approach (Clinical Insights & Analytics)
Focus: Extracting medical truth, ensuring data integrity, and discovering biomarkers.

Phase 1: Domain-Driven Data Purification
Standard data cleaning techniques (like blind statistical imputation or IQR outlier dropping) often destroy the "medical truth" of healthcare datasets. All data preprocessing was strictly guided by clinical validity:

Target Leakage Prevention: Dropped ChestScan to prevent artificial accuracy inflation.

Dimensionality Reduction: Removed administrative noise (State) and non-cardiac variables (HIVTesting, FluVaxLast12) to focus purely on physiological and lifestyle predictors.

Medical Integrity (Listwise Deletion): Dropped all rows with missing values to ensure the model trains only on 100% verified patient data, avoiding dangerous biases from imputation.

Clinical Validation vs. Statistical Outliers: Standard IQR methods flagged 1,10,000+ entries as "outliers." Domain analysis confirmed these are actually high-risk patients (e.g., BMI up to 100, or 30 days of poor health). Only 5 records were removed due to biological impossibility (e.g., SleepHours > 24).
