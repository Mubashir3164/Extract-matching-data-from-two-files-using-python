# Extract matching data from two files using python
> This script is written in Python and uses the pandas library to extract matching data from two files.
```
# Importing the necessary libraries
import pandas as pd

# Reading the first file
df1 = pd.read_csv('File1.txt', sep='\t', encoding='latin1')
```
The script uses the pd.read_csv() function to read a file named 'File1.txt'. It assumes that the file is a tab-separated values (TSV) file (as indicated by sep='\t') and is encoded in Latin-1 (as indicated by encoding='latin1'). The data from this file is loaded into a pandas DataFrame called df1.

```
# Reading the second file
df2 = pd.read_csv('File2.txt', sep='\t', encoding='latin1')
```
Similarly, the script reads another file named 'File2.txt' using pd.read_csv(). The assumptions about the file format and encoding are the same as in the previous step. The data from this file is loaded into a pandas DataFrame called df2.
```
# Extracting matching data
matching_data = df2[df2['column1'].isin(df1['column1'])]
```
The script extracts the matching data from df2 by filtering rows where the 'column1' column value is present in the 'column1' column of df1. This is done using the isin() function. The resulting filtered data is stored in a new DataFrame called matching_data.
```
# Saving the extracted data
matching_data.to_csv('extracted_data.txt', sep='\t', index=False)
```
Finally, the extracted data is saved to a text file named 'extracted_data.txt' using the to_csv() method of the matching_data DataFrame. The sep='\t' argument specifies that the values should be separated by tabs in the output file, and index=False ensures that the row index is not included in the saved file

> To use this script with your own data, follow these steps.
- Prepare your data files
- Ensure you have two input files: one with the list of column names to extract and another with the data to extract with the same column names.
- Make sure your input files are in a compatible format, such as tab-separated values (TSV) or comma-separated values (CSV).
- Verify that the column names in your data files match the column names used in the script ('e.g. any name such as Specie').
- Optionally, adjust the encoding parameter (encoding='latin1') if your data has a different encoding.
