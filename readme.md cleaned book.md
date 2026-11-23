# Books Web Scraping and Data Cleaning Task

This repository contains the web scraping and data cleaning workflow for book records, organized into separate notebooks/components as required.

## Project Structure

- **Scraping Notebook & Raw Data:** Dedicated notebook for collecting raw book data and exporting `scraped_books.csv`.
- **Cleaning Notebook & Cleaned Data:** Dedicated notebook for cleaning `scraped_books.csv` and exporting `cleaned_books.csv`.
- **Documentation:** This `README.md` file summarizing the workflow, schema, and cleaning results.

## Dataset Schema

The final cleaned dataset (`cleaned_books.csv`) contains **1,000 rows** and **4 columns**:

| Column | Type | Description |
| :--- | :--- | :--- |
| `Category` | `object` (`str`) | Book category formatted with leading/trailing whitespace removed and title casing applied. |
| `Title` | `object` (`str`) | Book title with leading/trailing whitespace trimmed. |
| `Price` | `float64` | Book price in GBP with the `£` symbol removed and cast to a numeric floating-point value. |
| `In_Stock` | `object` (`str`) | Stock availability status normalized with trimmed whitespace and consistent title casing. |

## Data Cleaning Steps

1. **Data Inspection:** Loaded `scraped_books.csv` (1,000 rows, 4 columns) and checked shape, sample records, and missing values (0 missing values found).
2. **Text Normalization:** Stripped extra whitespace across `Category`, `Title`, and `In_Stock`, and standardized casing on `Category` and `In_Stock`.
3. **Price Conversion:** Removed the `£` currency symbol and whitespace from `Price`, then converted values to `float64` using `pd.to_numeric`.
4. **Deduplication & Consistency Check:** Checked for duplicate records (0 duplicates removed) and verified data types and value consistency.
5. **Export:** Saved the verified dataset to `cleaned_books.csv` without the index column.

## Cleaning Summary

- **Initial Rows:** 1,000
- **Duplicates Removed:** 0
- **Missing Values:** 0 across all columns
- **Final Shape:** `(1000, 4)`
- **Output File:** `cleaned_books.csv`
