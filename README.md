# Read_folder_in-pyton
Read folder and merge multiple excel sheets
```import os
import pandas as pd

# Directory containing the Excel files
directory = 'C:\\Users\\neha.rathi\\Desktop\\FL Vendor merge file'

# Name of the sheet to read the data from
data_sheet = 'attachment_vprakash'

# Initialize an empty DataFrame to store the merged data
merged_data = pd.DataFrame()

# Iterate over the Excel files in the directory
for filename in os.listdir(directory):
    if filename.endswith(".xlsx"):
        file_path = os.path.join(directory, filename)
        df = pd.read_excel(file_path, sheet_name=data_sheet, header=1)  # Read the data from the specified sheet, excluding the first row of headings
        merged_data = pd.concat([merged_data, df], ignore_index=True)

# Save the merged data to a new Excel file
merged_data.to_excel('Merged_Data.xlsx', index=False)```

