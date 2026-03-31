# Data-Cleaning
# Call List Data Cleaning

## Overview
This project contains a cleaned version of a raw call list dataset. The original data was preserved in the `Call List` sheet, and the cleaned output was created in a separate sheet called `Cleaned Call List`.

## Cleaning Steps

### 1. Preserved the raw data
The original dataset was kept unchanged to maintain a source-of-truth version for comparison and auditing.

### 2. Removed unnecessary columns
The `Not_Useful_Column` field was excluded from the cleaned dataset because it did not add value to the final output.

### 3. Standardized text fields
Name fields were cleaned by:
- trimming extra spaces
- removing leading and trailing special characters
- fixing inconsistent text formatting

Examples:
- `/White` → `White`
- `...Potter` → `Potter`
- `Flenderson_` → `Flenderson`

### 4. Standardized phone numbers
Phone numbers were converted into a consistent format:

`(###) ###-####`

This included normalizing values that originally used:
- dashes
- slashes
- pipe symbols
- no separators

Examples:
- `123/643/9775` → `(123) 643-9775`
- `876|678|3469` → `(876) 678-3469`
- `7066950392` → `(706) 695-0392`

### 5. Normalized categorical values
Values in fields such as `Paying Customer` and `Do_Not_Contact` were standardized to consistent `Yes` / `No` labels.

Examples:
- `Y` → `Yes`
- `N` → `No`

### 6. Handled missing values
Missing and blank values were filled with:

`Not Available`

This ensures consistency across the cleaned dataset and makes the file easier to use for analysis or downstream processing.

### 7. Standardized placeholder null values
Entries such as `N/a` were treated as missing values and replaced with `Not Available` in the cleaned output.

### 8. Removed duplicate rows
Exact duplicate records were removed from the final cleaned dataset to avoid redundancy.

## Final Output
The cleaned dataset:
- keeps the raw data intact
- removes unnecessary columns
- standardizes text and phone formats
- normalizes categorical values
- fills missing values consistently
- removes duplicates

## Files / Sheets
- `Call List` → original raw dataset
- `Cleaned Call List` → final cleaned dataset
