# 🛢 Oil & Gas Daily Production Prediction

## 📌 Overview
This project builds a **machine learning pipeline** to predict **daily oil-well production** using a compact dataset of well characteristics, drilling information, and production history.  
The goal is to create an accurate model that can assist operations teams in **maintenance planning**, **resource allocation**, and **production optimization**.

**Best Model Achieved:** Random Forest Regressor  
**Test R²:** 0.9892 | **Test MSE:** 182.96

---

## 📂 Dataset
- **File:** `Oil_Well_dataset.csv`
- **Size:** ~800 rows, multiple well records
- **Key Columns:**
  - `WellID` — Unique well identifier
  - `Depth` — Depth of the well
  - `YearDrilled` — Year the well was drilled
  - `WellType` — Categorical (type of well)
  - `Geology` — Categorical (geological classification)
  - `Production` — Daily production (target variable)
  - `Age` — Engineered feature: current year - YearDrilled
  - `ProductionPerDepth` — Engineered feature: Production / Depth

---

## 🔄 Workflow
1. **Data Loading & Exploration**
   - Missing value check
   - Statistical summaries
   - Distribution plots
   - Correlation analysis

2. **Feature Engineering**
   - `Age` from `YearDrilled`
   - `ProductionPerDepth` ratio
   - One-hot encoding for `WellType` & `Geology`
   - Standard scaling of numerical features

3. **Feature Selection**
   - Variance Inflation Factor (VIF) analysis
   - SelectKBest (chi-squared)
   - ANOVA F-test

4. **Modeling**
   - **Linear Regression**
   - **Decision Tree Regressor**
   - **Random Forest Regressor**
   - **Gradient Boosting Regressor**

5. **Evaluation**
   - Metrics: Mean Squared Error (MSE), R² Score
   - Train/test split: `test_size=0.2, random_state=42`

---

## 📊 Model Performance

| Model                   | Train MSE | Train R² | Test MSE | Test R² |
|-------------------------|-----------|----------|----------|---------|
| Linear Regression       | 8351.94   | 0.5056   | 8351.94  | 0.5056  |
| Decision Tree           | 0.0       | 1.0000   | 388.83   | 0.9770  |
| Random Forest           | 26.82     | 0.9984   | 182.96   | 0.9892  |
| Gradient Boosting       | 283.81    | 0.9832   | 283.81   | 0.9832  |

✅ **Random Forest Regressor** achieved the best generalization on the test set.

---

## 📈 Visualizations
- Feature correlation heatmap
- Predicted vs Actual production plots
- Feature importance (tree-based models)
- Model comparison bar chart

*(See `notebook/Updated_Oil_and_Gas_Domain.ipynb` for plots.)*

---

## 🚀 Installation & Usage

```bash
# Clone the repository
git clone https://github.com/your-username/oil-gas-production-prediction.git
cd oil-gas-production-prediction

# Install dependencies
pip install -r requirements.txt
```
---

## 🧠 Next Steps
- Hyperparameter tuning with **GridSearchCV** / **RandomizedSearchCV**
- Cross-validation
- **SHAP** values for explainability
- Time-aware validation *(if more data available)*
- Deployment as REST API using **FastAPI** / **Flask**

---

## 🙏 Acknowledgements
A heartfelt thank you to **Kumar Sundram Sir** for his invaluable mentorship and guidance, and to the **Learnbay** team for providing an exceptional learning platform and support throughout this project.


---

## 📬 Contact
**Author:** Sourav Kumar 
**LinkedIn:** https://www.linkedin.com/in/sourav-kumar-5814341b8

# Run the notebook
jupyter notebook "Updated_Oil and Gas Domain.ipynb"
