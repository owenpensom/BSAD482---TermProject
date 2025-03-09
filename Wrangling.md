****_Data Wrangling_****

**_1\. Vaccination Rates_**

### **1\. Loading the Dataset**

- The dataset was loaded using Python (Pandas library) from a CSV file (vaccination-coverage-map.csv).

### **2\. Handling Missing Values**

- Missing values in the province column were filled with "Unknown".
- Missing numerical values (at_least_1_dose, partially_vaccinated, fully_vaccinated):
  - Forward filled (ffill) to propagate previous valid values.
  - Remaining missing values were filled with province-level averages using groupby() and transform().

### **3\. Removing Duplicates**

- Duplicate rows were identified and removed using the Pandas drop_duplicates() function.

### **4\. Standardizing Formats**

- The date column was converted to a datetime format using pd.to_datetime().
- Column names were standardized:
  - Renamed long column names to simpler names (e.g., numtotal_atleast1dose → at_least_1_dose).
  - Removed spaces and special characters and ensured consistent lowercase formatting.

### **5\. Filtering Unnecessary Data**

- Removed irrelevant columns, keeping only:
  - date, province, at_least_1_dose, partially_vaccinated, fully_vaccinated, percent_at_least_1_dose, and percent_fully_vaccinated.
- Filtered out rows with incomplete or irrelevant data.

### **6\. Joining Datasets**

- If applicable, joined the vaccination rates dataset with additional datasets (e.g., population data) to enhance the analysis.

### **7\. Aggregations**

- The dataset was aggregated to monthly averages:
  - Grouped by province and month using the pd.Grouper function for the date column.
  - Calculated monthly averages for numerical columns such as at_least_1_dose, partially_vaccinated, and fully_vaccinated.

### **8\. Pivoting**

- The dataset was pivoted to create a more analysis-friendly structure:
  - Ensured that province and month were the primary dimensions.

### **9\. Calculating Progress to Target**

- A new column, progress_to_target, was calculated:
  - Defined as (percent_fully_vaccinated / 90) \* 100 to measure progress toward the 90% vaccination target.

### **10\. Output**

- The cleaned and processed dataset was saved as a new CSV file (vaccination_cleaned.csv) for further analysis.

**_2\. Mobility Recovery Index_**

### **1\. Loading the Dataset**

- The dataset was loaded using Python (Pandas library) from an Excel file.

### **2\. Handling Missing Values**

- Missing values in the province column were replaced with "Unknown".
- Missing numerical values (retail, workplace, and residential):
  - Forward filled (ffill) to propagate previous valid values.
  - Remaining missing values were filled with the mean values for each province.

### **3\. Standardizing Formats**

- The Date column was converted to a datetime format using pd.to_datetime().
- Column names were standardized:
  - Renamed columns to simpler names (e.g., retail_and_recreation_percent_change_from_baseline → retail).
  - Removed spaces and special characters.

### **4\. Filtering Unnecessary Data**

- Unnecessary columns were dropped, keeping only:
  - Date, province, retail, workplace, and residential.
- Rows with irrelevant or incomplete data were filtered out.

### **5\. Aggregations**

- Data was aggregated to weekly averages:
  - Grouped by province and week using the pd.Grouper function.
  - Calculated weekly averages for retail, workplace, and residential.

**6\. Final Calculations**

- A new column, MRI (Mobility Recovery Index), was calculated:
  - The mean of the absolute values of retail, workplace, and residential.

### **7\. Output**

- The cleaned and aggregated dataset was ready for further analysis, with weekly trends and the calculated MRI for each province.

**_3\. Unemployment Rate Trends_**

### **1\. Loading the Dataset**

- The dataset was loaded using Python (Pandas library) from a CSV file (Unemployment_rates.csv).

### **2\. Handling Missing Values**

- The dataset was checked for missing values. However, no missing values were found in any column.

### **3\. Removing Duplicates**

- Duplicate rows were identified and removed using the Pandas drop_duplicates() function (if any existed).

### **4\. Standardizing Formats**

- The observation_date column was renamed to Date, and the LRUN64TTCAM156S column was renamed to Unemployment Rate for clarity.
- The Date column was converted to a datetime format using pd.to_datetime().

### **5\. Filtering Unnecessary Data**

- The dataset was filtered to include only rows where the Date was from **March 2019 onward**.
- Rows with irrelevant or incomplete data were filtered out (though none were found in this dataset).

### **6\. Aggregations**

- No additional aggregations were required as the data was already in a monthly format.

### **7\. Pivoting**

- Pivoting was not performed as the dataset was already in a straightforward structure.

### **8\. Visualizing Trends**

- A line plot was created to visualize the unemployment rate trends from March 2019 to the most recent date.

### **9\. Output**

- The filtered dataset was saved as a new CSV file (Unemployment_rates_filtered.csv).
- The file was made available for download.

**_4\. Public Heath Spending Changes_**

### **1\. Loading the Dataset**

- The dataset was uploaded by prompting the user using the files.upload() function in Google Colab.
- It was loaded from an Excel file (Healthcare_Spending.xlsx) using the Pandas library.

### **2\. Handling Missing Values**

- Missing numerical values in columns like Hospitals, Public Health, Administration, COVID-19 Response Funding, and Total were handled:
  - Non-numeric or placeholder values (e.g., "—", "–", "NaN") were replaced with NaN.
  - Remaining missing values were filled with 0 where applicable.

### **3\. Removing Duplicates**

- Duplicate rows were not explicitly mentioned but were assumed to be handled if necessary during the cleaning process.

### **4\. Standardizing Formats**

- The Year column was cleaned to retain only numeric values:
  - Non-numeric characters were removed using regular expressions.
  - Converted to integer format using astype(int).
- All numeric columns were converted to float for consistency.
- Column names were cleaned to remove special characters and line breaks.

### **5\. Filtering Unnecessary Data**

- Unnecessary sheets (e.g., Instructions, Contact info) from the Excel file were excluded.
- Only sheets corresponding to provinces (N.L., P.E.I., etc.) were processed.
- Irrelevant columns were filtered out, keeping only necessary ones:
  - Year, Hospitals, Public Health, Administration, COVID-19 Response Funding, Total, and Province.

### **6\. Joining Multiple Datasets**

- Data from multiple provincial sheets was combined into a single DataFrame using pd.concat().

### **7\. Aggregations**

- The dataset was filtered to include only records from 2020 onward (Year >= 2020).

### **8\. Output**

- The cleaned dataset was saved to a new CSV file (Filtered_Healthcare_Spending.csv) for further analysis.

**_5\. Economic Recovery Index_**

### **1\. Loading the Dataset**

- The dataset was uploaded by prompting the user using the files.upload() function in Google Colab.
- It was loaded from an Excel file (Healthcare_Spending.xlsx) using the Pandas library.

### **2\. Handling Missing Values**

- Missing numerical values in columns like Hospitals, Public Health, Administration, COVID-19 Response Funding, and Total were handled:
  - Non-numeric or placeholder values (e.g., "—", "–", "NaN") were replaced with NaN.
  - Remaining missing values were filled with 0 where applicable.

### **3\. Removing Duplicates**

- Duplicate rows were not explicitly mentioned but were assumed to be handled if necessary during the cleaning process.

### **4\. Standardizing Formats**

- The Year column was cleaned to retain only numeric values:
  - Non-numeric characters were removed using regular expressions.
  - Converted to integer format using astype(int).
- All numeric columns were converted to float for consistency.
- Column names were cleaned to remove special characters and line breaks.

### **5\. Filtering Unnecessary Data**

- Unnecessary sheets (e.g., Instructions, Contact info) from the Excel file were excluded.
- Only sheets corresponding to provinces (N.L., P.E.I., etc.) were processed.
- Irrelevant columns were filtered out, keeping only necessary ones:
  - Year, Hospitals, Public Health, Administration, COVID-19 Response Funding, Total, and Province.

### **6\. Joining Multiple Datasets**

- Data from multiple provincial sheets was combined into a single DataFrame using pd.concat().

### **7\. Aggregations**

- The dataset was filtered to include only records from 2020 onward (Year >= 2020).

### **8\. Output**

- The cleaned dataset was saved to a new CSV file (Filtered_Healthcare_Spending.csv) for further analysis.  
