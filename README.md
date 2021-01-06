# Melbourne Transport of various suburbs - DATA-INTEGRATION-AND-RESHAPING
Integrating the data from different files and reshaping it using various scaling/ transformation methods.  Technologies Used:- Python  Packages Used:- pandas, zipfile, shapefile, difflib, re, shapely.geometry, sklearn, sklearn.linear_model, BeautifulSoup
# Introduction
This assignment comprises of the integrate several datasets into one single schema and find and fix possible problems in the data.. We are provided with six input files, out of which two are in .zip, one .xlsx, one .txt, one .xml& one in _[.csv] (Comma Separated Values) file formats.

Main task is to integrate the contents of the data in the following files.

1. Data Integration

2. Data Reshaping

More details for each task will be given in the following sections.

# Methodology
For completing the given tasks, we had used the following steps.

1. Data Integration Here we had integrated the given datasets from the given input files & scraping the data from websites to generate the output schema as follows:

ID - Gives the unique ID of the property.
Address - Gives the address of the property.
Suburb - Gives the suburb name of the property which is calculated from Vic_suburb_boundary.zip., using lat & lon from the given data.
Price - Gives the price of the property.
Type - Gives the type of the property.
Date - Gives the date of the property sold.
Rooms - Gives the number of bedrooms present in the property.
Bathroom - Gives the number of bathrooms present in the property.
Car - Gives the number of parking spaces present in the property.
LandSize - Gives the area of the property.
Age - Gives the age of the property during selling time.
Latitude - Gives the latitude of the property.
Longitude - Gives the longitude of the property.
train_station_id - Gives the closest train station from the property which has a direct trip to Southern Cross Station.
distance_to_train_station - Gives the direct distance from the closest train station to the property.
travel_min_to_CBD - Gives the average time taken by the direct train which has a direct trip to Southern Cross Station on weekdays taht departs between 7 to 9.30 AM
over_priced? - Gives the boolean feature whether the price of the property is higher than median price of similar properties (with respect to bedrooms, bathrooms, parking_space, and property_type attributes) in the same suburb on the year of selling.
crime_A_average - Gives the average of type A crime in the local government area where the property is situated.
crime_B_average - Gives the average of type B crime in the local government area where the property is situated.
crime_C_average - Gives the average of type C crime in the local government area where the property is situated.
closest_primary_school - Gives the name of the closest primary school to the property.
distance_to_closest_primary - Gives the direct distance between the property and the closest primary school.
primary_school_ranking - Gives the ranking of the closest primary school to the property which is scraped from the website. If the school is not listed, append the value as "not ranked".
closest_secondary_school - Gives the name of the closest secondary school to the property.
distance_to_closest_secondary - Gives the direct distance between the property and the closest secondary school.
secondary_school_ranking - Gives the ranking of the closest secondary school to the property which is taken from xml file since scraping takes credentials which leads to security issues. If the school is not listed, append the value as "not ranked".
2. Data Reshaping Here we started reshaping the data by using standardisatiion & transformation techniques on given attributes.

Z-Score Normalisation (standardisation) - Using scikit library & the class we used is the StandardScaler class gives the scaled value.
Min-Max Normalization - Using scikit library & the class we used is the MinMaxScaler class gives the scaled value.
Tranformation - Used to compress the values in the dataframe for better prediction using 3 different techniques:

Root transformation - Finding the square root value of the dataset & building the linear model from the obtained data.
Square power transformation - Finding the powered value of the dataset & building the linear model from the obtained data.
Log transformation - Finding the logarithmic value of the dataset & building the linear model from the obtained data.
