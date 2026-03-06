End-to-End Cardiovascular Risk Prediction: From Clinical Insights to Production ML

🎯 Problem Statement

Cardiovascular diseases are a top cause of global deaths.

The goal is to build an end-to-end predictive system using population health survey data.

This project connects Clinical Data Science (finding physiological patterns) and Machine Learning Engineering (building a ready-to-use prediction pipeline) for early medical help.

📊 Dataset Information

Source: CDC Behavioral Risk Factor Surveillance System (BRFSS) 2022.

Initial Size: 4,45,132 patient records.

Final Cleaned Size: 3,13,269 high-quality patient records.

Target Variable: HadHeartAttack (Binary).

🔬 Part 1: The Data Science Approach (Clinical Insights & Analytics)

Focus: Extracting medical truth, ensuring data quality, and finding disease markers.

Standard cleaning methods (like blind math guesses or standard outlier drops) often ruin the "medical truth" of healthcare data.

All data cleaning in this project strictly followed clinical rules.

Target Leakage Prevention: Dropped ChestScan to stop fake high accuracy.

Reducing Columns: Removed location data (State) and non-heart variables (HIVTesting, FluVaxLast12) to focus only on body and lifestyle factors.

Medical Integrity: Dropped all rows with missing values to train the model only on 100% verified patient data, avoiding bad guesses.

Handling Outliers: Standard math flagged 1,10,000+ entries as errors, but medical checks proved they are actual high-risk patients (like a BMI of 100).

Final Drops: Only 5 records were removed for being physically impossible (like sleeping more than 24 hours).
