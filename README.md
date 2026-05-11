## Geospatial Heatmaps using Los Angeles Crime Data from 2020 to Present

## Description
This dataset presented an extensive amount of information about crimes that have occurred in Los Angeles County since the year 2020 up to around April 01 2025, it being updated bi-monthly. The Los Angeles Crime Data was used for a report and slide deck in my Statistics 140XP course at UCLA. 

## Methods
It was my endeavor to produce visualizations that would give insight into where selected crimes (Assault with Deadly Weapon, Criminal Homicide, and Rape, Forcible, and Rape, Attempted) occurred using windows of time (24 hours, 05:00 AM to 12:00 PM, 12:00 PM to 08:00 PM, and 08:00 PM to 05:00 AM). This would involve using several variables in the dataframe, subsetting, and partitioning. 

Subsetting was used to filter out rows that had NULL values for necessary columns using the double bracket notation in Python. As my team was concerned with how "sunny" a time of day was when crime occurred, I utilized a RBF (Gaussian) kernel that was "centered" at 12:00 PM with a 0.03 decay rate for a "Sunny" feature. This is to state that we set noon to be the highest value in the "Sunny" metric and as the time deviated from this, it would decrease in value. Data standardization was applied to missing values (e.g. turning 1 into 0001 for 12:01 AM), and an "Hour" column was developed for input into the "Sunny" feature. 

## Results
Using statistical tests, we concluded that there were no significant differences in the time of day for the amounts of crime done for the entire set of crimes or for subsets. This was supported by the visuals presented in this project, as there were constant crimes of each time throughout the duration of any time partioning applied. 

## Tools
Python
Jupyter Notebook
NumPy
Pandas
Matplotlib
Scikit-Learn

## Use
 Anaconda should be downloaded and with it, Jupyter notebooks should be a familiar topic to any user that wants to use this project. The dataset was downloaded from the Los Angeles Open Data Website, and it is under the CC0 1.0 Universal Legal Code License. This specific visualization project falls under the MIT License and should be treated accordingly.

Features
DR_NO - Division of Records Number: Official file number made up of a 2 digit year, area ID, and 5 digits - Text data
Date Rptd - MM/DD/YYYY - Floating Timestamp
DATE OCC - MM/DD/YYYY - Floating TimestampTIME OCC
TIME OCC - In 24 hour military time - Text data
...
Crm Cd - Indicates the crime committed. (Same as Crime Code 1) - Text data
Crm Cd Desc - Defines the Crime Code provided - Text data
...
LAT - Latitude - Numeric data
LON _ Longitude - Numeric data


## References
Géron, Aurélien. *Hands-on Machine Learning with Scikit-Learn, Keras, and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems*. 3rd ed., O’Reilly Media, 2022.

## Dataset Citation
LAPD. (2020, February). Crime Data from 2020 to Present, Last Updated March 19, 2025. Retrieved March 2025 from https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8/about_data
