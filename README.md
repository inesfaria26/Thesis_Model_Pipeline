🧠 Radiomics & Machine Learning Pipeline for Brain Metastasis Recurrence Prediction
-----------------------------------------
This repository contains the open-source implementation of a complete radiomics and machine learning pipeline developed as part of a Master’s thesis.
The goal of this project is to predict the recurrence of brain metastases after radiotherapy by combining imaging-based radiomics features with clinical data.

-----------------------------------------
🔍 Project Overview
-----------------------------------------
Brain metastases are a common complication in cancer patients, and radiotherapy is one of the primary treatment modalities. However, not all metastases respond equally, and recurrence remains a major challenge.
This project aims to support clinical decision-making by developing predictive ML models capable of identifying which lesions are likely to require a second irradiation (SI).

The pipeline integrates:
-CT and MRI preprocessing
-Image registration
-Isodose and tumor mask generation
-Radiomics feature extraction (PyRadiomics)
-Clinical feature integration
-Delta-radiomics computation
-Machine learning model training, tuning, and evaluation

-----------------------------------------
🧬 Dataset Summary
-----------------------------------------
Due to privacy constraints, image data are not included in this repository.

Key dataset characteristics:
-97 original patients from two institutions (Brazil and Argentina)
-53 patients included in final analysis after preprocessing
-415 brain metastases (subset used after QC)

Imaging modalities: CT, MRI (treatment + follow-up)
Clinical variables: age, sex, primary tumor site, number of metastases, treatment machine, among others
Train/test split: 80% / 20%

-----------------------------------------
🤖 Machine Learning Models
-----------------------------------------

Five supervised ML algorithms were tested:
-Random Forest
-AdaBoost
-XGBoost
-Support Vector Machine (SVM)
-Decision Tree

Model optimization included:
-One-Hot Encoding of categorical variables
-RandomizedSearchCV
-5-fold Cross-Validation

Best performing models:
Random Forest and AdaBoost (Accuracy ≈ 0.97 on test set)

-----------------------------------------
📁 Repository Contents
-----------------------------------------
├── preprocessing/         # CT/MRI preprocessing, registration, masks
├── radiomics/             # PyRadiomics feature extraction
├── clinical/              # Clinical data processing and integration
├── modeling/              # ML model training, tuning, and evaluation
├── results/               # Example outputs (features, metrics, plots)
└── README.md

-----------------------------------------
🚀 How to Use
-----------------------------------------
(Optional — only if you want; I can add setup instructions with conda, pip, requirements.txt, etc.)
Let me know if you want a runnable template.

-----------------------------------------
📌 Notes
-----------------------------------------
The pipeline is research-oriented and not intended for clinical use.

Original imaging data cannot be shared due to privacy and institutional regulations.

The codebase is modular to facilitate replication and extension.

Important clarification regarding the dataset:
Although the cohort included 53 patients, the machine learning models do not use patients as units of analysis — they use individual brain metastases.
After preprocessing, quality control, and exclusions, the final dataset contained 177 valid instances (metastases).
These were split into 80% training and 20% testing, resulting in 36 test cases, which correspond to the samples shown in the confusion matrices.
Cross-validation (5-fold) was applied only to the training set, ensuring robust hyperparameter tuning while preserving the integrity of the held-out test set.

-----------------------------------------
📝 Citation
-----------------------------------------
If you use this repository in your work, please cite:

Faria, I. (2025). Pipeline and Model Optimization to Predict Brain Metastases Recurrence After Radiation Therapy Treatment. Master’s Thesis.

-----------------------------------------
🙌 Acknowledgements
-----------------------------------------
Special thanks to:

Dr. Crystian Saraiva and Rodrigo Cardozo for data access

Supervisors and collaborators involved in model development
