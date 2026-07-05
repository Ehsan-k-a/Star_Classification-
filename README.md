# 🌌 Astronomical Object Classification using Machine Learning

A machine learning project that classifies astronomical objects into **Stars**, **Galaxies**, and **Quasars (QSOs)** using data from the Sloan Digital Sky Survey (SDSS).

---

## 📖 Project Overview

Astronomical surveys generate millions of observations that require automatic classification. This project develops and compares multiple machine learning models to accurately classify celestial objects using photometric and spectroscopic measurements.

The project follows a complete end-to-end machine learning workflow, including:

- Data cleaning
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model development
- Model comparison
- Hyperparameter tuning
- Performance evaluation

---

## 📊 Dataset

- **Source:** Sloan Digital Sky Survey (SDSS)
- Approximately **100,000 observations**
- Three target classes:
  - ⭐ Star
  - 🌌 Galaxy
  - ✨ Quasar (QSO)

### Features

- alpha
- delta
- u
- g
- r
- i
- z
- redshift

Metadata columns such as object IDs and telescope identifiers were removed because they do not contribute to predictive learning.

---

## 🧹 Data Preprocessing

The preprocessing pipeline includes:

- Removing unnecessary metadata columns
- Detecting invalid placeholder values (-9999)
- Replacing invalid values with NaN
- Removing affected records
- Validating that no missing or invalid values remain
- Label encoding target classes
- Stratified train-test split
- Feature scaling (Logistic Regression only)

---

## 📈 Exploratory Data Analysis

EDA includes:

- Class distribution
- Feature correlation matrix
- Redshift distribution
- Redshift by object class

These analyses provide insight into feature relationships and class characteristics before model development.

---

## 🤖 Models Evaluated

- Logistic Regression
- Random Forest
- XGBoost
- Tuned Random Forest (RandomizedSearchCV)

---

## 🏆 Results

| Model | Accuracy |
|--------|----------|
| Logistic Regression | **95.84%** |
| Random Forest | **97.98%** |
| XGBoost | **97.79%** |
| **Tuned Random Forest** | **98.08%** |

The Tuned Random Forest achieved the highest classification accuracy while maintaining excellent precision, recall, and F1-score across all classes.

---

## 🛠 Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

---

## 🚀 How to Run

Clone the repository

```bash
git clone https://github.com/yourusername/Astronomical-Object-Classification.git
```

Install dependencies

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

Open

```
Astronomical_Object_Classification_SDSS.ipynb
```

---

## 📌 Key Findings

- Proper preprocessing significantly improved data quality.
- Random Forest outperformed both Logistic Regression and XGBoost.
- Hyperparameter tuning further improved Random Forest performance to **98.08%**.
- Redshift is the most informative feature for distinguishing stars, galaxies, and quasars.

---

## ⚠ Limitations

- The model relies heavily on the redshift feature.
- Future work could evaluate classification using only photometric measurements.
- Deep learning approaches on raw astronomical images could also be explored.

---
## Future Work: Photometry-Only Classification

A future extension of this project would be to remove the redshift feature and evaluate model performance using only photometric measurements such as u, g, r, i, and z. Since redshift was identified as the dominant predictive feature, this experiment would test how well machine learning models can classify stars, galaxies, and quasars when spectroscopic information is unavailable.

This would create a more challenging and realistic scenario, as many large-scale astronomical surveys contain photometric observations but may not always include reliable redshift measurements. Models such as Random Forest, XGBoost, and neural networks could be retrained using only photometric features, and their performance could be compared against the current redshift-inclusive model.

This future work would help determine whether accurate astronomical object classification is possible using brightness and colour information alone, making the project more applicable to real-world survey conditions where spectroscopic data may be limited or expensive to obtain.

---

## 📄 License

MIT License
