# sales Analysis - Data Cleaning Summary

This project involves cleaning and preparing the `sales_data_sample.csv` dataset for analysis. Below is a summary of all the changes and cleaning steps performed on the dataset:

## Before Cleaning - Dataset Statistics

**Original Dataset Condition:**
- Run the "Capture statistics BEFORE cleaning" cell in the notebook to see:
  - Total number of rows in the original dataset
  - Total number of columns
  - **Total missing values**: Count of all NULL/NaN values across all columns
  - **Missing values per column**: Breakdown of missing values by column
  - **Total duplicate rows**: Number of exact row duplicates found

This information helps understand the data quality issues that were addressed during the cleaning process.

## Data Cleaning Steps

1. **Loaded the Dataset**
   - Used `pandas.read_csv` with `encoding='latin1'` to handle special characters.

2. **Identified and Handled Missing Values**
   - Checked for missing values in each column using `.isnull().sum()`.
   - Filled missing values with the mode (most frequent value) of each column using `df.fillna(df.mode().iloc[0])`.
   - After cleaning, there are no missing values in the dataset.

3. **Removed Duplicate Rows**
   - Removed exact duplicate rows using `df.drop_duplicates()`.
   - After cleaning, there are no duplicate rows in the dataset.

4. **Standardized Text Values**
   - If present, standardized the `gender` column to lowercase and replaced 'f'/'m' with 'female'/'male'.
   - If present, standardized the `country` column to title case and removed extra spaces.

5. **Converted Date Formats**
   - Identified columns containing 'date' in their name and converted them to a consistent datetime format using `pd.to_datetime`.

6. **Renamed Column Headers**
   - Cleaned and standardized column headers to be lowercase, with spaces replaced by underscores, and removed special characters.

7. **Checked and Fixed Data Types**
   - If the `age` column exists, converted it to integer type, replacing invalid or missing values with 0.

8. **Saved Cleaned Data**
   - Exported the cleaned DataFrame to `cleaned_sales_data_sample.csv` for further analysis or sharing.

---

