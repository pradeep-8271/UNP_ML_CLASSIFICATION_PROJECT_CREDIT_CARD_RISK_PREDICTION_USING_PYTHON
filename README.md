# Credit Card Risk Classification & Approval Analysis

## 📌 Project Overview
This project performs exploratory data analysis (EDA) and risk classification on a credit card application dataset. By analyzing applicant demographics, financial history, and employment sectors, the workflow uncovers key behavioral patterns and predictive indicators driving credit card approval decisions. I completed this project in collaboration with United Network Of Professionals (UNP) on Steel Industry Energy Consumption Using Python.This is a group project completed as part of our internship. The material link the project is :
GOOGLE COLAB FILE LINK: https://drive.google.com/file/d/1fw1JK3kanptnis9bokN46ca2eJ8U3b72/view?usp=sharing
PROJECT PRESENTATION FILE LINK: https://docs.google.com/presentation/d/1ERqWL-gEkYYHLqnU_1R_VpgBn9Dyf50O/edit?usp=sharing&ouid=109298726136836996811&rtpof=true&sd=true
## 📁 Dataset Description
The dataset (`clean_dataset.xlsx`) contains applicant profiles and credit history records. Key attributes include:
* **Demographics & Background:** `Gender`, `Age`, `Married`, `Citizen`, `Ethnicity`, `ZipCode`
* **Employment & Financials:** `Industry`, `Employed`, `Income`, `BankCustomer`, `YearsEmployed`, `PriorDefault`, `CreditScore`, `Debt`
* **Application Details:** `DriversLicense`
* **Target Variable:** `Approved` (`0` = Rejected, `1` = Approved)

## 🛠️ Technologies & Libraries Used
* **Python 3.x**
* **Data Manipulation:** `numpy`, `pandas`
* **Data Visualization:** `matplotlib`, `seaborn`

## 📊 Workflow & Methodology

### 1. Import Libraries & Data Exploration
* Loaded the dataset (`clean_dataset.xlsx`) using `pandas` and previewed initial records.
* Inspected dataset dimensions (`690` rows, `16` columns), column names, data types, and non-null counts.
* Verified data integrity by checking for missing values (`0` missing entries) and duplicate rows (`0` duplicates).

### 2. Pre-Processing (Before EDA)
* **Feature Dropping:** Removed non-predictive identifier columns (`ZipCode`) to reduce noise.
* **Cardinality Reduction:** Evaluated high-cardinality categorical columns (`Industry`, `Citizen`, `Ethnicity`). Consolidated 14 granular `Industry` categories into 6 broader macroeconomic sectors (`Finance & Business`, `Industrial & Manufacturing`, `Consumer & Retail`, `Public & Healthcare`, `Tech & Media`, and `Other`) mapped to `Industry_Group`.
* **Target Balance Inspection:** Analyzed the distribution of the target variable `Approved` to check for class imbalance (`55.5%` Rejected vs. `44.5%` Approved).

### 3. Exploratory Data Analysis (EDA)
* **Univariate Analysis:**
  * Plotted histograms (`bins=20`) across all continuous numerical features (`Age`, `Debt`, `YearsEmployed`, `CreditScore`, `Income`) to examine distributions and skewness.
  * Generated countplots and pie charts to visualize the overall approval vs. rejection ratio.
* **Bivariate & Multivariate Analysis:**
  * Created pairplots, KDE-overlaid histograms, and pairwise scatterplots segmented by `Approved` status to observe feature separation across financial metrics.
  * Visualized categorical features (`Gender`, `Married`, `BankCustomer`, `Industry_Group`, `PriorDefault`, `Employed`, `DriversLicense`, `Citizen`, `Ethnicity`) against `Approved` using grouped countplots.
* **Correlation Analysis:**
  * Computed the numeric correlation matrix and visualized relationships using an annotated `coolwarm` heatmap to identify multicollinearity and strong linear predictors.

## 🚀 Key Insights
* **Prior Default Impact:** `PriorDefault` serves as one of the strongest differentiators in approval outcomes, heavily separating approved applicants from rejected ones.
* **Financial Indicators:** Applicants with higher `YearsEmployed`, `CreditScore`, and `Income` demonstrate noticeably higher approval concentrations, alongside strong positive correlations between `YearsEmployed` and `Age`.
* **Sector Distribution:** Consolidating `Industry` into `Industry_Group` revealed that `Industrial & Manufacturing` and `Public & Healthcare` represent the largest applicant segments while maintaining consistent approval proportions.

## 💻 How to Run
1. Clone the repository or download `Credit_Card_Risk_Classification.ipynb`.
2. Ensure `clean_dataset.xlsx` is located in your working directory (or update the file path in the `pd.read_excel()` cell).
3. Install the required dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn openpyxl
   ```
4. Launch Jupyter Notebook or Google Colab and run all cells sequentially.
