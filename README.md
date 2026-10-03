# Heart Disease Prediction: Exploratory Data Analysis

Exploratory data analysis and preprocessing of a clinical heart disease dataset (918 patients, 11 features) using Python. The goal is to understand which patient characteristics are associated with heart disease and to prepare clean, model-ready data.

## Dataset

- **Source:** [Heart Failure Prediction Dataset (Kaggle)](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
- **Rows:** 918 | **Columns:** 12 (11 features + 1 target)
- **Target:** `HeartDisease` (1 = heart disease, 0 = normal)

| Feature | Type | Description |
|---|---|---|
| Age | Numeric | Age of the patient (years) |
| Sex | Categorical | M / F |
| ChestPainType | Categorical | TA, ATA, NAP, ASY |
| RestingBP | Numeric | Resting blood pressure (mm Hg) |
| Cholesterol | Numeric | Serum cholesterol (mg/dl) |
| FastingBS | Binary | 1 if fasting blood sugar > 120 mg/dl, else 0 |
| RestingECG | Categorical | Normal, ST, LVH |
| MaxHR | Numeric | Maximum heart rate achieved |
| ExerciseAngina | Categorical | Y / N |
| Oldpeak | Numeric | ST depression induced by exercise |
| ST_Slope | Categorical | Up, Flat, Down |
| HeartDisease | Binary | Target variable |

## What this notebook covers

1. **Data inspection:** shape, dtypes, summary statistics, missing values, duplicates
2. **Target check:** class balance (508 with heart disease vs 410 without, fairly balanced)
3. **Univariate analysis:** histograms with KDE for numeric features
4. **Data cleaning:** `Cholesterol` and `RestingBP` contained `0` values, which are physiologically impossible and represent missing data. These were replaced with the mean of the non-zero values.
5. **Bivariate analysis:** countplots of categorical features vs `HeartDisease`, boxplots of numeric features vs `HeartDisease`
6. **Correlation analysis:** heatmap of numeric features
7. **Encoding:** one-hot encoding of categorical features using `pd.get_dummies`

## Key findings

> Fill these in after checking your own plots. Examples of the kind of insight to write:

- Patients with `ExerciseAngina = Y` and `ST_Slope = Flat` show a much higher share of heart disease.
- `ChestPainType = ASY` (asymptomatic) is the most common type among patients with heart disease.
- Patients with heart disease tend to have a lower `MaxHR` and higher `Oldpeak`.
- Male patients show a higher proportion of heart disease than female patients in this dataset.

## Tech stack

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

## Project structure

```
heart-disease-prediction/
├── data/
│   └── heart.csv
├── notebooks/
│   └── heart_disease_eda.ipynb
├── requirements.txt
└── README.md
```

## How to run

```bash
git clone https://github.com/<your-username>/heart-disease-eda.git
cd heart-disease-eda
pip install -r requirements.txt
jupyter notebook notebooks/heart_disease_eda.ipynb
```

## Next steps

- Train and compare Logistic Regression, Random Forest, and XGBoost
- Evaluate with accuracy, precision, recall, F1, and ROC-AUC (recall matters most in a medical setting)
- Feature importance analysis
- Build a small Streamlit app for predictions

## Author

**Arpita**
MCA (Data Science & AI)
[GitHub](https://github.com/<arpitatandon-ds>) | [LinkedIn](https://linkedin.com/in/<arpita-tandon-31b3b7267>)
