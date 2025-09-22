# Data Cleaning and Preprocessing

## 📌 Description  

This project is part of a **Data Analyst Internship Task**.  
The dataset used is **KaggleV2-May-2016 (Medical Appointment No Shows)**  , which contains information about patients, their scheduled appointments, and whether they showed up or not.  

The main objective of this task was to **clean and preprocess the raw dataset** to make it analysis-ready. The Steps included are handling PatientId format, fixing date columns, standardizing text values, renaming columns, and checking for data quality issues.  

The final cleaned dataset (**Cleaned_KaggleV2.xlsx**)  is consistent , structured, and ready for further analysis or visualization.

## Key tasks performed

- Converted column names into a consistent snake_case format.
- Fixed PatientId formatting by converting it to text (to prevent digit loss).
- Standardized date fields (scheduled_day, appointment_day) into dd-mm-yyyy format.
- Normalized categorical values (e.g., M → Male, F → Female).
- Verified data quality: no missing values and no duplicate rows.
- The final cleaned dataset is well-structured, consistent, and analysis-ready.

## 📊 Dataset

- Source: Medical Appointment No-Shows dataset
- Raw file: <a href="https://github.com/sabaribala2004-dataanalyst/Data-Cleaning-and-Preprocessing/blob/main/KaggleV2-May-2016.csv">raw_data</a>
- Cleaned file: <a href="https://github.com/sabaribala2004-dataanalyst/Data-Cleaning-and-Preprocessing/blob/main/Cleaned_KaggleV2.xlsx">cleaned_data</a>

# 🛠️ Data Cleaning Steps

## Column Renaming
- Converted all column headers to lowercase with underscores.  
- Example:  
  - `PatientId` → `patient_id`  
  - `No-show` → `no_show`

## Patient ID Fix
- Converted scientific notation values to plain text.  
- Stored `patient_id` as text since it is only an identifier.

## Date Columns Standardization
- Removed `T` and `Z` characters from date/time fields.  
- Converted to proper Excel format → **dd-mm-yyyy**.

## Text Standardization
- Normalized `gender` values:  
  - `M` → `Male`  
  - `F` → `Female`

## Data Type Validation  

- Ensured correct data types:  
  - `age` → integer  
  - `patient_id` → string  
  - date columns → datetime  

## Outlier Check  

- Verified that age values fall within a realistic range (0–120).  
- Found 1 record with age = -1, which was invalid → removed.  
- Confirmed no other extreme or unrealistic values remained. .  

## Consistency Checks  

- Validated that `scheduled_day` is always ≤ `appointment_day`.  
- Added a new column `date_consistency` with three categories:  
  - `Before` → scheduled_day < appointment_day  
  - `Same Day` → scheduled_day = appointment_day  
  - `After (Error)` → scheduled_day > appointment_day  
- Found 4 records where `scheduled_day` was greater than `appointment_day`.  
- These invalid rows were removed from the cleaned dataset to ensure logical consistency.  


## Data Quality Check
- Verified **no missing values**.  
- Verified **no duplicate rows**.


## 📂 Output
- <a href="https://github.com/sabaribala2004-dataanalyst/Data-Cleaning-and-Preprocessing/blob/main/Cleaned_KaggleV2.xlsx">cleaned_data</a> → final processed dataset, ready for analysis/visualization.  


## ✅ Status
The dataset has been successfully **cleaned, validated, and stored in a structured format** for further use.  
This ensures reliable results in downstream tasks such as:  
- Data analysis  
- Dashboarding  
- Machine learning  
