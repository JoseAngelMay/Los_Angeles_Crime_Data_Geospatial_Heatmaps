# Geospatial Heatmaps using Los Angeles Crime Data from 2020 to Present

## Description
#### This dataset presented an extensive amount of information about crimes that have occurred in Los Angeles County since the year 2020 up to the present, it being updated bi-monthly. The Los Angeles Crime Data was used for a report and slide deck in my Statistics 140XP course at UCLA. It was my endeavor to produce visualizations that would give insight into where selected crimes (Assault with Deadly Weapon, Criminal Homicide, and Rape, Forcible, and Rape, Attempted) occurred using windows of time (24 hours, 05:00 AM to 12:00 PM, 12:00 PM to 08:00 PM, and 08:00 PM to 05:00 AM). This would involve using several variables in the dataframe, subsetting, and partitioning. 

#### A lot of data was present, but some instances lacked true coordinates (presented not by a NULL value but instead by a 0 value in coordinates, which would imply it takes place outside of Los Angeles County) and there were many more instances than were needed for my class's report and slide deck. Therefore, a good amount of subsetting was necessary, as was partitioning. In order to do this, a subset of the dataframe was made by selecting all instances that did not have 0 values in either coordinate - this way we have a truly geospatial subset of crime occurrences. Afterwards, based on a variable that mentions crime name ("Crm Cd Desc"), in conjunction with a feature extracted column ("Hour") that was derived from a present feature ("TIME OCC"), and also coordinates ("LAT" and "LON"), a heatmap was able to be produced using these geospatially available instances. 

#### The key aspects to attain the appropriate visualizations involved using the dataframe's plot method as well as using a second constructed feature ("Sunny"), which applied an RBF (Gaussian) kernel to the constructed "Hour" variable to noon with a decay rate of 0.03. The "Hour" variable was constructed by adjusting all "TIME OCC" values to have a length of 4, so 0 values were appended to the front if the length was not 4 (e.g. turning 1 to 0001, turning 500 to 0500, et cetera). This way, the first two characters in the string could be extracted so that we have an appropriate "Hour" column (e.g. 1301, 1323, and 1348 would all reflect in values of 13, 0801, 0815, and 0845 would all reflect a value of 8, et cetera). Using this, another column was produced by getting values (maximum of 1 and minimum of 0) from applying an RBF (Gaussian) kernel to this new "Hour" variable. This new column would be a "Sunny" feature, and was used as the "heat" of the heatmaps as it provided a way to visualize the amount of light during a crime's occurrence.

#### Python is used because of how it has one of the largest and ambitious communities, so it is not only user-friendly, but has a lot of libraries that help in data analysis and machine learning. NumPy was used because arrays are essential to anything and everything data analysis and machine learning in Python, and NumPy is also foundational to Pandas and Matplotlib. NumPy also provides several important transformations and applications throughout this project. Pandas provides tools to build off of and work with dataframes, which made it an essential library in this project. A dataframe was loaded into this Jupyter notebook through Pandas and this library provides methods and functions to check properties of each numeric and categorical column. Matplotlib provides several types of plotting tools and this helps guide individuals with what should be done and any trends and patterns that appear to be present. Seaborn was used to provide an important graph which also provided fitted linear regression items. Scikit-Learn was also used extensively, both for preprocessing data by cleaning, imputing, encoding, and setting up the items in the Jupyter notebook, but also to test out multiple algorithms and verify validity through root mean square error and k-fold cross-validation.

#### My goals arising from this experience are to better my visualizations. It was tedious, but very rewarding to produce these geospatial heatmaps, as they provided insight and patterns into real data. I hope to do this with more data.

## Use
#### Anaconda should be downloaded and with it, Jupyter notebooks should be a familiar topic to any user that wants to use this project. The dataset was downloaded from the Los Angeles Open Data Website, and it is under the CC0 1.0 Universal Legal Code License. This specific visualization project falls under the MIT License and should be treated accordingly.

## Features
#### DR_NO - Division of Records Number: Official file number made up of a 2 digit year, area ID, and 5 digits - Text data
#### Date Rptd - MM/DD/YYYY - Floating Timestamp
#### DATE OCC - MM/DD/YYYY - Floating TimestampTIME OCC
#### TIME OCC - In 24 hour military time - Text data
#### ...
#### Crm Cd - Indicates the crime committed. (Same as Crime Code 1) - Text data
#### Crm Cd Desc - Defines the Crime Code provided - Text data
#### ...
#### LAT - Latitude - Numeric data
#### LON _ Longitude - Numeric data


## References
#### Géron, Aurélien. *Hands-on Machine Learning with Scikit-Learn, Keras, and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems*. 3rd ed., O’Reilly Media, 2022.

## Dataset Citation
#### LAPD. (2020, February). Crime Data from 2020 to Present, Last Updated March 19, 2025. Retrieved March 2025 from https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8/about_data
