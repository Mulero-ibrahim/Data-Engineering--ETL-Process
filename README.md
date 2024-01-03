This script is an ETL (Extract, Transform, Load) process designed for extracting data from a webpage, transforming it, and then loading it into both a CSV file and a SQLite database. It also includes logging and running SQL queries on the loaded data.
1. Extract:
Function: extract(url, table_attribs)
Description: This function extracts data from a specified webpage. It takes a URL and a list of attributes for table columns. The function uses BeautifulSoup to parse the HTML content of the page and extract data from a specified table. The extracted data is then saved into a Pandas DataFrame.
2. Transform:
Function: transform(df, efx_path)
Description: This function transforms the extracted data. It converts the market capitalization values from USD to EUR, GBP, and INR using exchange rates from a CSV file. The transformed data includes new columns with these converted values.
3. Load:
Functions: load_to_csv(df, csv_path) and load_to_db(df, conn, table_name)
Description: The load_to_csv function saves the transformed data into a CSV file at the specified path. The load_to_db function loads the data into a SQLite database table, replacing the table if it already exists.
4. Run Query:
Function: run_query(conn, query_statements)
Description: This function executes a list of SQL queries on the database table and prints the results. It's useful for data verification and quick analysis.
5. Logging:
Function: log_progress(message)
Description: This function logs the progress of the ETL process by appending timestamped messages to a log file. It's useful for tracking the execution stages and troubleshooting.
6. Execution Flow:
The script begins with setting up a SQLite database connection.
It follows a sequential flow of ETL processes: first extracting data from a webpage, transforming the data, saving it to a CSV file, and loading it into a database.
After loading, the script executes predefined SQL queries to interact with the database.
Throughout the process, progress is logged to a file for monitoring and debugging purposes.
The script concludes by closing the database connection.
