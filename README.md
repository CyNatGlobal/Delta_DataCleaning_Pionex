# Delta_DataCleaning_Pionex
Pionex crypto dataset
Data Cleaning Script
Overview
This script is designed to clean a dataset by validating and standardizing specific columns: Email, Phone, and RegistrationDate. Invalid data is separated into a "junk file" for review. The script also handles missing values, removes duplicates, and standardizes column names by replacing spaces with underscores. This script is suitable for large datasets and is optimized for use in Google Colab.

Requirements
Python 3
Libraries: pandas, numpy, re, datetime
To run this code, make sure to install the required libraries (if not already installed in your environment).

Instructions
Upload the Data: Use files.upload() to upload your CSV file.
Standardize Column Names: All spaces in column names are replaced with underscores for easier referencing.
Email Validation: The script uses a regex pattern to identify invalid email addresses. Rows with invalid emails are moved to a separate junk_data file.
Registration Date Validation: Dates are converted to datetime format; rows with invalid or missing dates are removed from the main data and stored in junk_data.
Phone Number Validation: Phone numbers are standardized to a US format (assumed 10-digit numbers with an optional country code). Invalid numbers are removed from the main data and stored in junk_data.
Duplicates and Missing Values: Duplicate rows and remaining missing values are removed from the main data and stored in junk_data.
Save Cleaned Data and Junk Data: The cleaned data is saved as cleaned_data.csv, and invalid data (junk data) is saved as junk_data.csv.
Code Explanation
Here’s a breakdown of each section of the code:

Import Libraries: Import required libraries (pandas, numpy, re, datetime).
Load Data: Upload and load the CSV data into a DataFrame.
Standardize Column Names: Replace spaces in column names with underscores.
Set Up Junk DataFrame: Create a separate DataFrame (junk_data) to store invalid rows.
Validate Emails: Use regex to check for valid email patterns. Move invalid emails to junk_data.
Validate Registration Dates: Convert dates to datetime format. Rows with invalid dates are moved to junk_data.
Validate Phone Numbers: Standardize phone numbers to a specific format (e.g., +1xxxxxxxxxx). Move invalid phone numbers to junk_data.
Remove Duplicates and Handle Missing Values: Remove duplicate rows and rows with remaining missing values, adding these to junk_data.
Save Data: Save both the cleaned data and junk data as CSV files (cleaned_data.csv and junk_data.csv).
Files Generated
cleaned_data.csv: Contains only valid rows with standardized data.
junk_data.csv: Contains rows with invalid data (emails, phone numbers, or registration dates), duplicates, or missing values for review.
Example Usage
Run the code in Google Colab to execute the script as intended. After execution, cleaned_data.csv and junk_data.csv will be available for download.

Notes
This script assumes that phone numbers are in a 10-digit US format. Adjust the validate_phone function if the data includes international numbers.
The registration date format should be consistent; otherwise, customize the validate_date function as needed.
By following these instructions, you can use the script to clean your dataset effectively.
