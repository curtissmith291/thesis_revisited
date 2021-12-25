# Thesis Revisited

This project uses machine learning to re-evaluate the data used for my master's thesis. 

Function of files in directory:
- combine_files.ipynb --> Combines the raw .csv files found in raw_data
- data_cleaning.ipynb --> Prepared data for analysis to keep regression files cleaner; 
	added classifier columns
- logistic_regression.ipynb --> Initial logistic regression model


## Data Cleaning Steps
1) Convert old .xlxs files to .csv
	- The old data were stored in one .xlsx file per location, and formatted such they they were not viable for easy importation into a .csv. The .xlsx files included formulas to calculate the percent occurrence of each feature, a header that included the date and grouping identifier (as the set of grains' origin were unknown [double-blind] until after analysis so as to prevent bias), and a graph displaying occurrences. These features were removed so as to create a truly "raw data" file for each location that shows only the occurrence or non-occurrence of each feature, with one sand grain per row. 

2) Combine .csv files into one "master" raw data file
	- Using Jupyter Notebook, the raw .csv files were combined into one file. During combination, additional columns were added to the files, including a location and distance along the transect/river. The headers were also made consistent. 


## Machine Learning Algorithm Selection

The ultimate goal of this project is to train a model with our input data so that the model can then classify an unknown input as either one of four outputs: cold-dry, cold-wet, hot-dry, or hot-wet. 

Right away, regression type algorithms are excluded as the goal is to classify an input rather than numerical prediction. 

The most basic classification machine learning model is logistic regression which analyzes multiple input variables to predict binary outcomes. While the desired output for this project is ultimately a non-binary output, we can start simple and break up our desired outputs into two binary outcomes: cold-hot and wet-dry. 



 