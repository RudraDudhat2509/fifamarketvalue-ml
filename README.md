# fifamarketvalue-ml
Feature engineering on FIFA dataset with extensive text processing of player attributes, traits, and positions.

⚽ FIFA Feature Engineering: Extracting Real Value from Text
This project explores the FIFA player dataset with a focus on feature engineering, particularly from textual and semi-structured fields like positions, traits, contract info, and player metadata.

Instead of applying standard encoding, we build meaningful numerical features that reflect real-world football knowledge and translate into machine-learnable insights.

##📂 Dataset
Source: FIFA player data from KAGGLE(sampled for GitHub limits)

Target: Value_EUR — market value of each playe in euros

Rows: Sample of 1,000 shared due to size limits

Notebooks include full pipeline, from loading to modeling


## 🛠️ Core Contributions

- ⚙️ Cleaned and parsed semi-structured text fields like:  
  `Position`, `Work Rate`, `Traits`, `Body Type`
- 🧠 Engineered features such as:  
  `BaseRating`, `ContractLength`, `is_prodigy`, `Total stats`, `BMI`
- 🧾 Extracted **boolean flags** from textual attributes such as:  
  `is_captain`, `has_trait_leadership`, `is_young`, `is_experienced`, `is_on_loan`, etc.
- 📊 Designed custom numeric features from string and ordinal fields  
- 🚫 Identified and excluded `Release clause_EUR` due to **target leakage**

##🔢 Model Performance
We trained a Random Forest Regressor to evaluate how well our engineered features predict player market value.

Metric	With Leakage (Release clause_EUR)	Without Leakage
MAE	3,346	5,354
RMSE	46,316	186,705
R² Score	0.99996	0.99939

⚠️ Release clause_EUR was removed due to suspected data leakage — it overlapped too closely with the target (Value_EUR). Even without it, the model explains 99.94% of the variance, validating the strength of the engineered features.

##📊 Feature Importance (No Leakage)
Top engineered features that contributed most to predicting player value:

BaseRating — composite of key base attributes

Potential — ceiling of player's development

Age, Wage_EUR

ContractLength, Weak foot, is_prodigy

Total skill, Total attacking, BMI, etc.

##🎯 SHAP Explainability
Used SHAP (SHapley values) to interpret the model’s behavior:

📌 Global feature importance

🔁 Direction of impact (does a feature push value up or down?)

🔍 Local explanations for individual players

Engineered features like Potential and ContractLength were not just statistically strong, but also interpretable and intuitive, confirmed by SHAP.

##📁 Project Structure
📦 fifa-feature-engineering
├── 📁 data
│   └── fifa_sample.csv
├── 📁 notebooks
│   └── feature_engineering.ipynb
├── 📄 requirements.txt
├── 📄 README.md


##🚀 Future Additions
 Streamlit or Gradio app for player value prediction

 Dashboard for SHAP explainability

 Notebook comparison of model types (XGBoost, LGBM, etc.)

##🙌 Author
Rudra Dudhat
BTech in Mechatronics
IIT Bhilai
GitHub: @rudradudhat
Kaggle: https://www.kaggle.com/rudrad7
