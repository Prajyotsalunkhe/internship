# Netflix Data Analysis and Cleaning

This repository contains the analysis and cleaning of the Netflix titles dataset (`netflix_titles.csv`). The Jupyter notebook `netflix.ipynb` performs data preprocessing steps to clean and prepare the data for further analysis. Below is a detailed documentation of the before and after changes applied during the cleaning process.

## Dataset Overview
- **Original File**: `netflix_titles.csv`
- **Cleaned File**: `cleaned_netflix_titles.csv`
- **Library Dependencies**: pandas, numpy

## Step-by-Step Changes

### 1. Loading the Dataset
- **Before**: Dataset not loaded.
- **After**: Dataset loaded into a pandas DataFrame (`df`) from `netflix_titles.csv`. Initial exploration includes displaying the first 10 rows, dataset info, and column names.

### 2. Renaming Column Headers
- **Before**: Column names may have inconsistent casing and spaces (e.g., original column names as per CSV).
- **After**: All column names converted to lowercase and spaces replaced with underscores for uniformity (e.g., 'Title' becomes 'title', 'Date Added' becomes 'date_added').

### 3. Checking for Duplicates
- **Before**: Unknown number of duplicate rows.
- **After**: Checked for exact duplicate rows. Result: Total number of exact duplicate rows printed (likely 0 based on typical datasets, but confirmed via code).

### 4. Handling Null Values (Before Cleaning)
- **Before**: Null value counts across columns (e.g., director, cast, country, rating, duration, date_added have varying nulls).
- **After**: Initial null counts displayed.

### 5. Handling Null Values (Cleaning Process)
- **Before**: Nulls present in 'director', 'cast', 'country', 'rating', 'duration', 'date_added'.
- **After**:
  - 'director', 'cast', 'country' filled with 'Unknown'.
  - Rows with nulls in 'rating', 'duration', 'date_added' dropped.
  - Final null counts displayed (should be 0 for the dropped columns).

### 6. Data Types Check
- **Before**: Data types as loaded from CSV.
- **After**: Data types of the cleaned DataFrame displayed (e.g., object for strings, datetime if applicable).

### 7. Displaying Cleaned Data
- **Before**: Raw data with inconsistencies.
- **After**: First few rows of the cleaned DataFrame displayed.

### 8. Date Format Conversion
- **Before**: 'date_added' column in original format (e.g., 'January 1, 2020').
- **After**: 'date_added' stripped of whitespace and converted to 'DD-MM-YYYY' format (e.g., '01-01-2020').

### 9. Saving Cleaned Dataset
- **Before**: No cleaned CSV file.
- **After**: Cleaned DataFrame saved to `cleaned_netflix_titles.csv` without index.

## Summary of Transformations
- **Input**: Raw Netflix titles dataset with potential duplicates, nulls, and inconsistent formatting.
- **Output**: Cleaned dataset with standardized column names, handled nulls, consistent date format, and no critical missing values.
- **Key Improvements**: Improved data quality for analysis, visualization, or modeling by ensuring uniformity and completeness.

## How to Run
1. Ensure pandas and numpy are installed (`pip install pandas numpy`).
2. Open `netflix.ipynb` in Jupyter Notebook or JupyterLab.
3. Run all cells to reproduce the cleaning process.
4. The cleaned file `cleaned_netflix_titles.csv` will be generated in the same directory.

## Notes
- All changes are performed in-place on the DataFrame.
- No external dependencies beyond standard Python data science libraries.
- If the dataset is updated, re-run the notebook to apply changes.
