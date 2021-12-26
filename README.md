# Thesis Revisited

This project uses machine learning to re-evaluate the data used for my master's thesis. 

Function of files in directory:
- combine_files.ipynb --> Combines the raw .csv files found in raw_data
- data_cleaning.ipynb --> Prepared data for analysis to keep regression files cleaner; added classifier columns
- summary_stastics.ipynb --> run and visualize summary statistics
- binary_modeling.ipynb --> Initial classification models for the binary outcomes of wet-dry and cold-hot

Function of sub-directories:
- outputs --> Destination directory for the output of scripts to protect against accidental overwriting of files
- raw_data --> Contains the uncleaned raw data
- working_data --> contains cleaned data files and files used in machine learning scripts


## Data Cleaning Steps
1) Convert old .xlxs files to .csv
	- The old data were stored in one .xlsx file per location, and formatted such they they were not viable for easy importation into a .csv. The .xlsx files included formulas to calculate the percent occurrence of each feature, a header that included the date and grouping identifier (as the set of grains' origin were unknown [double-blind] until after analysis so as to prevent bias), and a graph displaying occurrences. These features were removed so as to create a truly "raw data" file for each location that shows only the occurrence or non-occurrence of each feature, with one sand grain per row. 

2) Combine .csv files into one "master" raw data file
	- Using Jupyter Notebook, the raw .csv files were combined into one file. During combination, additional columns were added to the files, including a location and distance along the transect/river. The headers were also made consistent. 


## Statistical Analysis and Visualization

Prior to running machine learning models, data were statistically analyzed...

### Tests for Normality

As all the variables in the dataset are binary, they inherently cannot be normally distributed. 


## Machine Learning Algorithm Selection

The ultimate goal of this project is to train a model with our input data so that the model can then classify an unknown input as either one of four outputs: cold-dry, cold-wet, hot-dry, or hot-wet. 

Right away, regression type algorithms are excluded as the goal is to classify an input rather than numerical prediction. 

### Logistic Regression Modeling

The most basic classification machine learning model is logistic regression which analyzes multiple input variables to predict binary outcomes. While the desired output for this project is ultimately a non-binary output, we can start simple and break up our desired outputs into two binary outcomes: cold-hot and wet-dry. 

Logistic regression does not require some of the same assumptions for linear regression, i.e., linear relationship between the independent and dependent variables, the independent variables do are not required to be normally distributed, and homoscedasticity is not required.  

However, logistic regression requires (or at least performs best) when there is little to no multicollinearity among the independent variables. 

There are certain assumptions required to be met for the best performance of logistic regression models:

1) Binary logistic regression requires the dependent variable to be binary - met by this data set

2) No repeated observations of the same data - met by this data set

3) Little to no multicollinearity among the independent variables; meeting this assumption will be the most difficult for the data used in this project. To address multicollinearity, collinearity between independent variables will be tested using Variance Inflation Factor (VIF). Additionally, the model will be run using differing variations of the independent variables. 

4) Assumption of linearity of independent variables and log odds - this is only required for continuous independent variables. 

5) Requires large sample size - >1000 data points are included in this data set 


### Support Vector Machines Modeling






 