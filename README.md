# Customer Sales Data Cleaning with Python & Pandas

## Project Overview
This project demonstrates an end-to-end data cleaning workflow on a deliberately messy customer sales dataset.

The goal was to inspect the raw data, identify quality issues, clean inconsistent and invalid values, handle missing data, convert data types, remove duplicates, and export a cleaned dataset ready for further analysis.

## Dataset
- Raw rows: 10,200
- Raw columns: 12
- Final rows: 9,027
- Final columns: 12

### Columns
`Customer_ID`, `Name`, `Gender`, `Age`, `City`, `Signup_Date`, `Last_Purchase_Date`, `Purchase_Amount`, `Feedback_Score`, `Email`, `Phone_Number`, `Country`

## Problems Identified
- Missing values in several customer fields
- Duplicate records
- Repeated `Customer_ID` values
- Inconsistent age values such as text-formatted values
- Invalid age values
- Extreme/invalid purchase amounts (`9999999` and negative `-500`)
- Inconsistent gender formatting (`M`, `Male`, `F`, `Female`, casing/whitespace)
- Inconsistent city/country formatting
- Abbreviated country value (`Ind`)
- Date columns stored as strings
- Missing last-purchase dates

## Cleaning Workflow
1. Loaded the raw CSV with Pandas.
2. Inspected structure and data types using `info()`.
3. Reviewed descriptive statistics using `describe()`.
4. Measured missing values.
5. Checked full-row duplicates and repeated customer IDs.
6. Removed rows with missing `Customer_ID`.
7. Cleaned and validated `Age`.
8. Replaced invalid age values with missing values and filled missing ages using the median.
9. Identified and replaced invalid purchase amounts, then filled missing purchase amounts using the median.
10. Filled missing feedback scores using the mode.
11. Standardized gender values and filled missing gender values.
12. Standardized city names and filled missing city values.
13. Standardized country values, corrected `Ind` to `India`, and filled missing country values.
14. Converted date columns to datetime.
15. Forward-filled the remaining missing last-purchase date.
16. Removed duplicate rows after cleaning.
17. Verified the final dataset and exported it as a new CSV.

## Tools
- Python
- Pandas
- NumPy
- Matplotlib

## Result
The final dataset contains **9,027 rows and 12 columns**. All columns are populated except for **1 remaining `Last_Purchase_Date` value** in the exported result.

The notebook contains the full inspection and cleaning process, while the raw and cleaned CSV files allow the before/after result to be compared directly.

## Files
- `messy_customer_sales_data.csv` — original messy dataset
- `cleaned_customer_sales_data.csv` — cleaned dataset
- `cleaned_customer.ipynb` — Jupyter Notebook containing the cleaning workflow
- `README.md` — project documentation

## Next Step
This cleaned dataset can be used for exploratory data analysis (EDA), visualization, statistical analysis, and eventually dashboarding.
