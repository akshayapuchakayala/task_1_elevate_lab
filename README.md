# Task 1: Data Cleaning and Preprocessing

## Objective

The objective of this task is to clean and preprocess a raw dataset by identifying and handling missing values, removing duplicate records, standardizing text values, converting date formats, renaming column headers, and verifying data types. The cleaned dataset is then prepared for further analysis and machine learning.

## Dataset

**Dataset Name:** Customer Personality Analysis

The dataset contains customer demographic information, purchasing behavior, and marketing campaign responses.

## Tools Used

* Python
* Pandas
* Jupyter Notebook

## Data Cleaning Steps Performed

### 1. Loaded the Dataset

* Imported the dataset using Pandas.
* Since the dataset is tab-separated, it was loaded using:

  ```python
  pd.read_csv("marketing_campaign.csv", sep="\t")
  ```

### 2. Checked Dataset Information

* Displayed the first few rows using `head()`.
* Checked dataset information using `info()`.
* Examined summary statistics using `describe()`.

### 3. Handled Missing Values

* Identified missing values using:

  ```python
  df.isnull().sum()
  ```
* Filled missing values in the `income` column with the median value:

  ```python
  df["income"] = df["income"].fillna(df["income"].median())
  ```

### 4. Removed Duplicate Records

* Checked duplicate rows using:

  ```python
  df.duplicated().sum()
  ```
* Removed duplicate records using:

  ```python
  df.drop_duplicates(inplace=True)
  ```

### 5. Standardized Text Values

* Standardized the `education` and `marital_status` columns by removing extra spaces and converting text to title case.

### 6. Renamed Column Headers

* Converted all column names to lowercase.
* Removed leading/trailing spaces.
* Replaced spaces with underscores.

### 7. Converted Date Format

* Converted the `dt_customer` column from string (`object`) to `datetime` using:

  ```python
  pd.to_datetime()
  ```

### 8. Verified Data Types

* Checked data types using:

  ```python
  df.dtypes
  ```
* Confirmed all numeric columns were correctly stored as `int64` or `float64`.
* Converted the `dt_customer` column to `datetime64[ns]`.

### 9. Saved the Cleaned Dataset

* Exported the cleaned dataset as:

  ```
  cleaned_customer_data.csv
  ```

## Files Included

* `marketing_campaign.csv` (Original Dataset)
* `cleaned_customer_data.csv` (Cleaned Dataset)
* `data_cleaning.py` 
* `README.md`

## Learning Outcomes

* Learned how to identify and handle missing values.
* Removed duplicate records.
* Standardized categorical text data.
* Renamed column headers using a consistent naming convention.
* Converted date columns to the correct datetime format.
* Verified and corrected data types.
* Prepared the dataset for further analysis and machine learning.

## Conclusion

The dataset was successfully cleaned and preprocessed by handling missing values, removing duplicates, standardizing text fields, converting date formats, renaming column headers, and verifying data types. The final cleaned dataset is ready for data analysis, visualization, and machine learning applications.
