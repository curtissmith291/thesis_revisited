# Thesis Revisited

This project uses machine learning to re-evaluate the data used for my master's thesis. 


## Data Cleaning Steps
1) Convert old .xlxs files to .csv
	- The old data were stored in one .xlsx file per location, and formatted such they they were not viable for easy importation into a .cvs. The .xlsx files included formulas to calculate the percent occurrence of each feature, a header that included the date and grouping identifier (as the set of grains' origin were unknown [double-blind] until after analysis so as to prevent bias), and a graph displaying occurrences. These features were removed so as to create a truly "raw data" file for each location that shows only the occurrence or non-occurrence of each feature, with one sand grain per row. 