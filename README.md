# ETL Script for Webpage Data Extraction, Transformation, and Loading

## Overview

This script is designed for an ETL (Extract, Transform, Load) process that involves extracting data from a webpage, transforming it, and loading it into both a CSV file and a SQLite database. The script also incorporates logging functionalities and the ability to run SQL queries on the loaded data.

## Functions

### Extract Function: `extract(url, table_attribs)`

This function extracts data from a specified webpage. It takes a URL and a list of attributes for table columns. Using BeautifulSoup, it parses the HTML content of the page and extracts data from a specified table. The extracted data is then saved into a Pandas DataFrame.

### Transform Function: `transform(df, efx_path)`

This function transforms the extracted data by converting market capitalization values from USD to EUR, GBP, and INR using exchange rates from a CSV file. The transformed data includes new columns with these converted values.

### Load Functions: `load_to_csv(df, csv_path)` and `load_to_db(df, conn, table_name)`

- `load_to_csv` saves the transformed data into a CSV file at the specified path.
- `load_to_db` loads the data into a SQLite database table, replacing the table if it already exists.

### Run Query Function: `run_query(conn, query_statements)`

This function executes a list of SQL queries on the database table and prints the results. It's useful for data verification and quick analysis.

### Logging Function: `log_progress(message)`

This function logs the progress of the ETL process by appending timestamped messages to a log file. It's useful for tracking the execution stages and troubleshooting.

## Execution Flow

The script begins by setting up a SQLite database connection. The sequence of operations includes:

1. **Extract:** Data is extracted from a webpage using the provided URL and table attributes.
2. **Transform:** The extracted data is transformed, converting market capitalization to different currencies.
3. **Load to CSV:** The transformed data is saved into a CSV file.
4. **Load to Database:** The data is loaded into a SQLite database table, replacing it if it already exists.
5. **Run Queries:** Predefined SQL queries are executed on the database table for interaction and verification.
6. **Logging:** Progress is logged throughout the process for monitoring and debugging purposes.
7. **Conclusion:** The script closes the database connection.

This structured approach ensures a systematic execution of the ETL process, making it efficient and reliable.

