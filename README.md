# Netflix Content Analysis using PySpark

## Overview

This project performs an in-depth analysis of Netflix's content dataset using PySpark. The analysis includes content filtering, handling missing values, categorical and temporal analysis, and extracting insights related to content duration. The goal is to explore and summarize key trends in Netflix's library, including content type distribution, country-based content analysis, content addition trends over the years, and movie duration characteristics.

## Prerequisites

- Apache Spark with PySpark library
- Python 3.x
- Jupyter Notebook or any Python IDE

## Steps Involved

### 1. **Dataset Ingestion and Initial Exploration**

- The dataset `netflix_titles.csv` is ingested using Spark's `read.csv` function.
- Basic data exploration is performed, including printing the schema and the first few rows of the data.

### 2. **Data Cleaning and Preparation**

- **Null Value Handling**: Missing values in key columns are replaced with default placeholders such as "Uncredited", "Global", and "Untitled Content".
- **Strict Validation**: Rows with null values in essential columns (e.g., `type` and `title`) are removed.
- **Type Casting**: Ensures `release_year` is in integer format and extracts the numeric duration from the `duration` column.

### 3. **Categorical Analysis**

- A categorical analysis is performed on the `type`, `country`, `rating`, and `listed_in` columns, counting the distinct categories in each column.
- The results give insights into the variety of content types, countries, and ratings available on Netflix.

### 4. **Country-based Content Distribution**

- The dataset is grouped by `country`, and the content count per country is calculated.
- The top 5 countries with the most content are displayed.

### 5. **Temporal Analysis of Content Additions**

- The `date_added` column is parsed into a proper date format (`MMMM d, yyyy`).
- Entries with invalid dates are filtered out, and the year of addition is extracted for analysis.
- The distribution of content additions by year is displayed to observe patterns over time.

### 6. **Duration Analysis for Movies**

- The `duration` column is processed to extract numeric values, which are converted to integers.
- The average duration of movies is calculated, giving insights into the typical length of Netflix movies.

## Results and Insights

The analysis produces the following insights:
- **Content Type Distribution**: Breakdown of distinct content types, countries, and ratings.
- **Top 5 Countries with Most Content**: Identification of the countries with the highest number of Netflix entries.
- **Temporal Distribution**: Trends in the number of content additions by year.
- **Average Movie Duration**: Insights into the typical length of Netflix movies.

## Running the Analysis

To run the analysis:
1. Ensure that Spark is properly installed and configured.
2. Place the `netflix_titles.csv` file in the working directory.
3. Execute the Python code in a Jupyter Notebook or Python IDE.

## Dependencies

- `pyspark`
- `pandas` (for any further analysis or optional CSV file handling)
- `matplotlib` (optional, for visualizations)

## Conclusion

This project demonstrates how to analyze large datasets using PySpark, focusing on Netflix content. It provides valuable insights into the structure and characteristics of Netflix's content library, enabling better understanding of content trends, additions, and movie durations.
