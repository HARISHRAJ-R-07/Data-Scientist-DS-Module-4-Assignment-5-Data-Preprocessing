# 🩺 Diabetes Data Preprocessing

A complete **Data Preprocessing** project built with Python for preparing a healthcare diabetes dataset for machine learning workflows.

The notebook covers data inspection, cleaning, missing-value imputation, duplicate handling, outlier analysis, categorical encoding, and feature scaling.

## 📌 Project Overview

The dataset contains patient and laboratory information collected from multiple healthcare sources. The preprocessing workflow addresses common real-world data-quality issues such as:

- Missing values
- Duplicate records
- Inconsistent categorical values
- Extreme numerical values / outliers
- Different feature scales
- Categorical variables that need numerical encoding

## 🎯 Objectives

- Load and inspect the diabetes dataset
- Understand numerical and categorical features
- Clean inconsistent column names and categorical values
- Handle missing values
- Remove duplicate records
- Analyze and handle outliers
- Encode categorical features
- Apply feature scaling
- Prepare data for subsequent machine-learning analysis

## 🗂️ Dataset

The dataset contains **1,009 records** and includes the following fields:

| Column | Description |
|---|---|
| `Visit_ID` | Visit identifier |
| `Patient_ID` | Patient identifier |
| `Gender` | Patient gender |
| `AGE` | Patient age |
| `Urea` | Urea measurement |
| `Cr` | Creatinine measurement |
| `HbA1c` | HbA1c measurement |
| `Chol` | Cholesterol measurement |
| `TG` | Triglycerides measurement |
| `HDL` | HDL measurement |
| `LDL` | LDL measurement |
| `VLDL` | VLDL measurement |
| `BMI` | Body Mass Index |
| `CLASS` | Diabetes class: N, P, or Y |

## 🔄 Preprocessing Workflow

### 1. Data Loading & Inspection
- Loaded the dataset using Pandas.
- Checked `head()`, `tail()`, shape, columns, `info()`, and data types.
- Identified numerical and categorical columns.

### 2. Data Cleaning
- Removed the unnecessary `Unnamed: 0` column.
- Renamed:
  - `ID` → `Visit_ID`
  - `No_Pation` → `Patient_ID`
- Checked unique categorical values.
- Standardized `Gender` values such as `f` → `F`.
- Standardized selected `CLASS` values.
- Generated descriptive statistics.

### 3. Missing-Value Handling
- Numerical missing values were imputed using `SimpleImputer` with the **mean** strategy.
- Missing `Gender` values were filled using the **mode**.
- Missing-value counts were checked after imputation.

### 4. Duplicate Handling
- Checked for duplicate rows.
- Found duplicate records and removed them using `drop_duplicates()`.

### 5. Outlier Analysis
- Visualized numerical distributions using Seaborn box plots.
- Retained outliers in:
  - `AGE`
  - `HbA1c`
  - `BMI`
- Applied percentile-based thresholds to:
  - `Cr` → 99.5th percentile
  - `Urea` → 99.9th percentile
- Calculated IQR-based bounds for:
  - `LDL`
  - `VLDL`
  - `HDL`
  - `TG`
  - `Chol`

### 6. Encoding
- Used **LabelEncoder** for `Gender`.
- Used **OneHotEncoder** for `CLASS`.
- The notebook uses `handle_unknown="ignore"` for one-hot encoding.

### 7. Feature Scaling
The notebook demonstrates two scaling approaches for:

`Patient_ID`, `AGE`, `BMI`, and `Cr`

- **StandardScaler** — standardization
- **MinMaxScaler** — normalization

Both transformed outputs are generated in the notebook for comparison.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab / Jupyter Notebook

## 📁 Repository Structure

```text
├── Data_Preprocessing.ipynb
├── diabetes.csv
├── preprocessed_encoded.csv
├── requirements.txt
└── README.md
```

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <your-repository-folder>
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Run:

```bash
jupyter notebook Data_Preprocessing.ipynb
```

Or open the notebook directly in Google Colab.

### 4. Keep the dataset in the same folder

Make sure `diabetes.csv` is available in the working directory before running the notebook.

## 📊 Key Preprocessing Techniques

| Technique | Purpose |
|---|---|
| `SimpleImputer` | Handle missing numerical values |
| Mode imputation | Handle missing categorical values |
| `drop_duplicates()` | Remove duplicate records |
| Percentile threshold | Handle extreme `Cr` and `Urea` values |
| IQR | Calculate bounds for lipid-related features |
| `LabelEncoder` | Convert `Gender` into numeric values |
| `OneHotEncoder` | Convert `CLASS` into encoded columns |
| `StandardScaler` | Standardize selected numerical features |
| `MinMaxScaler` | Normalize selected numerical features |

## 📌 Learning Outcomes

Through this project, I practiced an end-to-end preprocessing workflow and strengthened my understanding of:

- Data quality assessment
- Missing-value treatment
- Categorical data cleaning
- Duplicate detection
- Outlier analysis
- Feature encoding
- Feature scaling
- Preparing structured data for machine learning

## 👨‍💻 Author

**Harish Raj**

Aspiring Data Scientist | Python | Data Analysis | Machine Learning

---

⭐ If you find this project useful, feel free to explore the notebook and preprocessing workflow.
