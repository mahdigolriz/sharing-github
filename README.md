## Project Name
Early detection of drilling pipe stuck incidents using machine learning methods and time series analysis

## Technologies
Project is created with:
* Jupyter Notebook: 6.1.3

## General Information
- First part of code ("Processing row data for each case") unifies and extracts a proper time series data set from row data (mud logging reports) for each case
- Secend part combines all outputs of first section for all cases
- Then, using tsfresh package final dataset is prepared and models are developed by different algorithms

## Required libraries and packages
*pandas-1.1.0
*numpy-1.19.1
*matplotlib-3.3.1
*tsfresh-0.18.0
*sklearn-0.0
*xgboost-1.4.2

## Usage
1- Save 'row data' folder
2- Open 'Processing row data for each case' code
3- Set working directory of 'row data' folder in first section of code
4- Run first section to combine all csv files in folder and providing master file (combined_csv.csv)
5- Section 2 - Read master file, select and rename porper columns (features) then remove NAN cells
6- Section 3 - Turn characteristics to numerical rounded values and datetime format
7- Section 4 - Build a single column dataframe which includes whole time steps (86400 seconds) of stuck or non-stuck day
8- Section 5 - Merge two dataframe
9- Section 6 & 7- fill miss data with up and down information
10- Section 8 & 9- Replace moving average information and plot them to stuck time recognition using visual analysis
11- Section 10- Build a single column dataframe which includes 2-hour time steps before stuck time (120 minutes)
12- Section 11- Replace moving average of all parametrs with original data to remove flactuations
13- Section 12- Merge 2-hour time steps dataframe with moving average features
14- Section 13- Interpolate inclination and DLS values using survey information
15- Section 14- Add inclination and DLS values to another moving average features
16- Section 15 & 16- Remove auxiliary columns and add id and time steps orders to be compatible with tsfresh package
17- Section 17- Export final dataset of each case

Above steps should be implemented on all cases
Only row data for one case was uploaded for test
Outputs of all cases including 100 excel file was uploaded in "All processed cases" folder

in second stage 'Stuck pipe modeling' code shoud be run
1- Save 'All processed cases' folder
2- Open 'Stuck pipe modeling' code
3- Set working directory of 'All processed cases' folder in first section of code to combine all cases ('df' file which is uploaded)
4- Section 2- Sort rows based on id and time steps
5- Section 3- Apply tsfresh package to extract time related descriptive features from time series of each parameter
6- Section 4- Read 'y' excel which includes targets or labels of each case (1 or 0) and turn it to a series
7- Section 5- Apply tsfresh package to extract most related and important desctiptive features from time series parameters (final modeling dataset)
8- Section 6- Import all machine learning algorithms
9- Develop different models and evalute them
