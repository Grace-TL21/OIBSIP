# ☕ Café Sales Data Cleaning

## 📌 Project Overview

This project focuses on cleaning and preparing a messy café sales dataset using Python and pandas.

The original dataset contained missing values, invalid placeholders, inconsistent data types, incorrect unit prices, and inconsistent transaction totals. A systematic data-cleaning process was applied to improve data quality and prepare the dataset for further analysis and visualisation.

---

## 🎯 Objective

The objective of this project is to perform professional-level data cleaning by:

- Identifying missing and invalid values
- Handling missing data using appropriate strategies
- Detecting duplicate records
- Correcting data types
- Standardising categorical values
- Detecting and evaluating outliers
- Identifying logical inconsistencies
- Validating transaction values
- Comparing data quality before and after cleaning
- Exporting a clean, analysis-ready dataset

---

## 📊 Dataset

The project uses the **Cafe Sales - Dirty Data for Cleaning Training** dataset from Kaggle.

The dataset contains **10,000 transactions** and the following 8 columns:

| Column | Description |
|---|---|
| Transaction ID | Unique identifier for each transaction |
| Item | Café product purchased |
| Quantity | Number of items purchased |
| Price Per Unit | Unit price of the product |
| Total Spent | Total transaction amount |
| Payment Method | Customer payment method |
| Location | Purchase location/type |
| Transaction Date | Date of transaction |

---

## 🛠️ Technologies Used

- Python
- pandas
- NumPy
- Jupyter Notebook

---

## 🔍 Data Quality Issues Identified

Initial inspection revealed several data-quality problems, including:

- **6,826 raw missing values**
- **3,256 invalid placeholders** such as `ERROR` and `UNKNOWN`
- Incorrect data types
- Missing categorical and numerical values
- Inconsistent unit prices
- Inconsistent transaction totals
- Potential statistical outliers

No exact duplicate rows were identified.

---

## 🧹 Data Cleaning Process

### 1. Initial Data Inspection

The dataset was inspected using:

- Dataset shape
- Column information and data types
- Missing-value counts
- Duplicate-row detection
- Unique-value inspection
- Numerical range checks

### 2. Invalid Value Handling

Invalid placeholders such as:

```text
ERROR
UNKNOWN
```

were identified and treated as missing values before further cleaning.

### 3. Missing Value Treatment

Different strategies were selected depending on the meaning and quality of each variable.

- Numerical transaction values were recovered where reliable relationships existed.
- Remaining numerical missing values were handled using median imputation.
- Unresolved categorical values were represented using an `Unknown` category where making an assumption could distort the data.
- Item values were carefully reviewed to avoid artificially increasing the frequency of the most common product.

### 4. Data Type Correction

Columns were converted to appropriate data types:

- `Transaction ID` → String
- `Item` → String
- `Quantity` → Integer
- `Price Per Unit` → Float
- `Total Spent` → Float
- `Payment Method` → String
- `Location` → String
- `Transaction Date` → Datetime

Final data type accuracy reached **100%**.

### 5. Categorical Data Standardisation

Categorical variables were reviewed for inconsistent formatting and invalid labels.

Unresolved categories were standardised as:

```text
Unknown
```

rather than making unsupported assumptions.

### 6. Price Consistency Validation

Unit prices were validated against the dominant price associated with each known café item.

After excluding unknown items, **27 inconsistent unit-price records** were identified and corrected using item-level pricing patterns supported by the dataset.

### 7. Transaction Total Validation

Transaction totals were validated using the relationship:

```text
Total Spent = Quantity × Price Per Unit
```

Inconsistent transaction totals were corrected after validating quantity and unit-price information.

### 8. Outlier Detection

The **Interquartile Range (IQR)** method was used to detect potential numerical outliers.

Statistical outliers were evaluated using logical transaction ranges rather than automatically removed.

Final validated ranges were:

| Variable | Minimum | Maximum |
|---|---:|---:|
| Quantity | 1 | 5 |
| Price Per Unit | $1.00 | $5.00 |
| Total Spent | $1.00 | $25.00 |

Values within these ranges were considered plausible café transactions and were retained.

---

## 📈 Before vs. After Cleaning

| Metric | Before Cleaning | After Cleaning |
|---|---:|---:|
| Row Count | 10,000 | 10,000 |
| Raw Missing Values | 6,826 | 0 |
| Invalid Placeholders | 3,256 | 0 |
| Missing + Invalid Values | 10,082 | 0 |
| Duplicate Rows | 0 | 0 |
| Data Type Accuracy | 50% | 100% |

> **Note:** Missing and invalid values represent cell-level data-quality issues. Therefore, their combined count can exceed the total number of rows because a single transaction may contain issues in multiple columns.

---

## ✅ Final Result

After cleaning, the final dataset contains:

- **10,000 rows**
- **8 columns**
- **0 missing values**
- **0 invalid `ERROR` / `UNKNOWN` placeholders**
- **0 duplicate rows**
- **100% appropriate data types**
- Validated numerical ranges
- Consistent transaction calculations

The cleaned dataset is ready for exploratory data analysis, visualisation, reporting, and further business analysis.

---

## 📁 Project Structure

```text
DataAnalytics-L1-DataCleaning/
│
├── Data_Cleaning.ipynb
├── dirty_cafe_sales.csv
├── cleaned_cafe_sales.csv
├── README.md
└── screenshots/
```

---

## ▶️ How to Run the Project

1. Clone or download this repository.
2. Open `Data_Cleaning.ipynb` in Jupyter Notebook.
3. Make sure `dirty_cafe_sales.csv` is available in the project directory.
4. Run the notebook cells from top to bottom.
5. The cleaned dataset will be exported as:

```text
cleaned_cafe_sales.csv
```

---

## 💡 Key Learning Outcomes

Through this project, I practised:

- Data quality assessment
- Missing-value treatment
- Data type conversion
- Categorical data standardisation
- Duplicate detection
- IQR-based outlier detection
- Business-rule-based data validation
- Data consistency checking
- Data cleaning documentation
- Exporting analysis-ready datasets

---

## 👩‍💻 Author

**Myo Thiri Lwin (Grace)**

Data Analytics Portfolio Project  
OASIS INFOBYTE Internship