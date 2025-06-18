## ETL Pipeline for Automated Excel File Processing

---

## 📌 Project Overview

This project automates the ETL (Extract, Transform, Load) process for Excel files dropped into a watched folder. The script detects new files, transforms their data, and loads them into a MySQL database, ensuring proper data integrity and preventing duplicates.

---

## 🔧 Technologies Used

✅ Python (Automation & Data Processing)

✅ Pandas (Excel File Handling & Data Transformation)

✅ SQLAlchemy (MySQL Database Connection)

✅ PyMySQL (Interacting with MySQL)

✅ Watchdog (File System Monitoring)

✅ Jupyter Notebook (Development & Debugging)

---

## 🛠 Installation Steps

Before running the script, make sure you have the necessary dependencies installed.

→ →  pip install pandas sqlalchemy pymysql watchdog openpyxl

---

## 🚀 How It Works

## 1️⃣ Watching for New Files

→  The script continuously monitors a folder (Pipeline_Automation) using the watchdog library.

→  When a new Excel file (.xlsx) is added, the event handler triggers the ETL process.

## 2️⃣ Extracting Data from Excel

→  Reads the file using pandas.read_excel().

→  Prints column data types to ensure consistency before processing.

## 3️⃣ Transforming Data

→  Splits Customer_ID into Customer_ID and Customer_Name.

→  Removes promotional entries (Customer_Name != 'Promo').

→  Converts Cookies_Shipped from string ($99.99) to float (99.99).

## 4️⃣ Preventing Duplicate Entries

→  Fetches existing Customer_ID & Order_ID from MySQL.

→  Ensures matching data types before merging to prevent errors.

→  Inserts only new records while skipping duplicates.

## 5️⃣ Loading Data into MySQL

→  Uses SQLAlchemy to establish a database connection.

→  Loads cleaned data into MySQL using df.to_sql().

## ⏯️ Running the Script

Run the script to start monitoring the folder:

→ →  python etl_pipeline.py

You should see output like this:

👀 Watching folder: C:\Users\DELL\Documents\Pipeline_Automation for new Excel files...
📂 New file detected: 2017 Order Data.xlsx
✅ ETL completed and data loaded into MySQL without duplicates.

---

## 🔎 Debugging & Logs

If any issues arise:

→  Check column types using df.dtypes.

→  Verify database connection with pymysql.connect().

→  Ensure MySQL is running (net start MySQL).

---

## 📌 Next Steps

→  Improve performance for handling large datasets.

→  Add logging to track errors & successful operations.

→  Expand functionality for CSV & JSON file support.

---

## 💡 Contributions
If you have ideas or improvements, feel free to submit a pull request or open an issue!

