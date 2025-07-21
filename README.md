# ❤️ Heart Disease Prediction

## 📁 About the Dataset

This is a **multivariate dataset** containing 14 commonly used attributes for heart disease prediction, extracted from the Cleveland dataset. Originally, the dataset had 76 features, but this refined version focuses on the most relevant ones.

The objective is twofold:
- ✅ Predict the presence of heart disease (target: `num`)
- 🔍 Perform data analysis to guide medical insight and modeling

---

## 📊 Dataset Features

| Column     | Description |
|------------|-------------|
| `id`       | Unique patient ID |
| `age`      | Age (in years) |
| `origin`   | Place of study |
| `sex`      | Gender |
| `cp`       | Chest pain type |
| `trestbps` | Resting blood pressure |
| `chol`     | Serum cholesterol (mg/dl) |
| `fbs`      | Fasting blood sugar > 120 mg/dl |
| `restecg`  | Resting ECG result |
| `thalach`  | Max heart rate achieved |
| `exang`    | Exercise-induced angina |
| `oldpeak`  | ST depression relative to rest |
| `slope`    | Slope of the peak exercise ST segment |
| `ca`       | Number of vessels colored by fluoroscopy (Dropped) |
| `thal`     | Thalassemia status (Dropped) |
| `num`      | Heart disease diagnosis (0 = no disease, 1–4 = present) |

---

## 🔧 Preprocessing Steps

- Missing data was handled using **Random Forest Imputation** (classifier/regressor depending on column type).
- Dropped high-missing and low-importance columns: `ca`, `thal`.
- Imputed values for `trestbps`, `chol`, `fbs`, `restecg`, `thalach`, `exang`, `oldpeak`, and `slope`.
- Outliers detected and handled using **IQR method** (for left-skewed) and **Z-score** (for normal distributions).
- Saved the cleaned data to `PREPROCESSED_DATA.pkl`.

---

## 🧪 Feature Classification

- **Categorical**: `slope`, `exang`, `restecg`, `fbs`, `cp`, `sex`, `num`
- **Boolean**: `fbs`, `exang`
- **Numeric**: `oldpeak`, `thalach`, `chol`, `trestbps`, `age`

---

## 🤖 Model Performance

| Model                         | Accuracy | Recall | F1 Score | AUC    | Time (s) |
|------------------------------|----------|--------|----------|--------|----------|
| Ridge Classifier             | 65.65%   | 65.65% | 60.54%   | —      | 0.097    |
| Logistic Regression          | 65.42%   | 65.42% | 63.82%   | —      | 1.112    |
| Random Forest                | 64.83%   | 64.83% | 63.07%   | 0.859  | 0.269    |
| Gradient Boosting            | 64.82%   | 64.82% | 62.99%   | —      | 0.703    |
| LightGBM                     | 62.99%   | 62.99% | 60.25%   | 0.841  | 0.530    |

Others include: LDA, Extra Trees, Decision Tree, KNN, Naive Bayes, SVM, QDA, AdaBoost.

---

## 📚 References

- Detrano et al. (1989) – *American Journal of Cardiology*
- Aha & Kibler – *Instance-based prediction using Cleveland database*
- Gennari et al. – *Incremental concept formation*

---

## 🙏 Acknowledgements

- **Hungarian Institute of Cardiology, Budapest**
- **University Hospital, Zurich & Basel**
- **Cleveland Clinic Foundation**
