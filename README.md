# GoodData-PerformanceTesting
ETL Performance Test (must be opened in CloudConnect): The workspace file used in CloudConnect there I built the three ldms used for testing as well as the graph that I uploaded to GoodData's secure server for testing. Since the file I accessed was massive (35 GB) I had to configure one of my components in the graph to obtain the URL of a secure server I deployed the file to via cyberduck.

Master File: A 35 GB CSV file with 20M rows and 100 columns: 50 text fields A1-A50 (attributes) and 50 numeric fields F1-F50 (facts)
All attribute values are strings of length 25.
A1: Row number ("0000000000000000000000000", "0000000000000000000000001", ..., "0000000000000000019999999")
A2: Row number mod 2 ("0000000000000000000000000", "0000000000000000000000001", "0000000000000000000000000", "0000000000000000000000001", ...)
A3: Row number mod 5 ("0000000000000000000000000", "0000000000000000000000001", "0000000000000000000000002", "0000000000000000000000003", "0000000000000000000000004", "0000000000000000000000000", ...)
A4: Row number mod 10
A5: Row number mod 20
A6: Row number mod 50
A7: Row number mod 100
A8: Row number mod 200
A9: Row number mod 500
...
A50: Row number mod 10M
All facts: Random numbers (two decimal places).

data_gen.py: used for uploading the first 10M rows 
append_data.py:uploading the last 10M
