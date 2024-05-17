# Atul_Jadhav_repo
# Given the Employee table below, Write a SQL query to fetch the count of
# employees by department with counts sorted in descending order.
SELECT department, COUNT(*) as employee_count
FROM Employee
GROUP BY department
ORDER BY employee_count DESC;

# Write a SQL query that returns the Department Names along with the unit price amount of the
# most expensive product sold in each respective department.
SELECT d.DepartmentName, MAX(p.UnitPrice) as max_unit_price
FROM Product p
JOIN Department d ON p.DepartmentID = d.ID
GROUP BY d.DepartmentName;

# Let’s say you have a CSV input file that contains thousands of credit card
# transactions.Write a simple block of Python code that (a) reads the input file (and all of its transactions) and
# (b) calculates the average transaction amount across all records.
 
import csv

with open('input_file.csv', 'r') as f:
    reader = csv.reader(f)
    transactions = [float(row[2]) for row in reader]

average_transaction_amount = sum(transactions) / len(transactions)
print(average_transaction_amount)

# Write a code snippet that generates the square of every element in the list lst in
# a pythonic way.

lst = [1, 2, 3, 4]
square = [x**2 for x in lst]
print(squares) 

# Given an integer array nums, write a Python function that returns True if the
# array has duplicates. Otherwise, the function should return False.

def has_duplicates(nums):
    return len(nums) != len(set(nums))

# 6. Bonous question
I would design a cloud-based ETL/ELT data pipeline using Apache Airflow and Google Cloud Storage. The pipeline would extract data from the legacy database using JDBC connector, transform the data using Apache Spark data processing capabilities, and load the data into a Google BigQuery for downstream analytics and reporting. The pipeline would also archive the raw sourced data and transformed output data in cloud storage, partitioned by export date.

# 8.
Tables/Entities:
Pharmacy: ID, Name, Address, Phone Number, Opening Hours.
Product: ID, Name, Description, Category, Price, Stock Quantity.
Employee: ID, Name, Role, PharmacyID, Contact Information.
Customer: ID, Name, Contact Information, Membership Details.
Prescription: ID, CustomerID, EmployeeID, Date, Details.
Transaction: ID, CustomerID, PharmacyID, Date, Total Amount, Payment Method.
Supplier: ID, Name, Contact Information, Products Supplied.
Inventory: PharmacyID, ProductID, Stock Level, Last Restocked.

Columns/Attributes:
Primary keys (e.g., ID).
Foreign keys (e.g., PharmacyID in Employee and Inventory tables).
Data types (e.g., INT, VARCHAR, DECIMAL).
Constraints (e.g., NOT NULL, UNIQUE).
Indexes for faster querying (e.g., on frequently searched columns).

Data Structures:
Normalized tables to reduce data redundancy.
Use of lookup tables for categories and statuses.

Constraints:
Ensuring data integrity with foreign key constraints.
Validation rules (e.g., positive stock levels, valid date ranges).

Metadata:
Timestamps for creation and modification dates.
User tracking for changes (e.g., last modified by).

