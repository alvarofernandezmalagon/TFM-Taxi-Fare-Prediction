
A Data Science project in Taxi Domain
===================
`#DataScience` `#PySpark` `#Python` `#MachineLearning` `#BigData` `#Spark` `#Taxi` `#Fare`


## Objetive

The main objective of this project is to try to predict the price that a taxi will cost us in Chicago based on the data of other trips made in this city and adding information about the weather. 

Note: This document briefly describes what has been carried out during this project and there is more detail in each of the notebooks.

### About the methodology 
The CRISP-DM (*cross-industry process for data mining*) methodology provides a structured approach to planning a data mining task and was applied to this data science project.

![CRISP-DM](Information/process.jpg)


## About the technology ##
#### Programming languages and interpreters

 - Spark Python API (**PySpark**) : Used practically throughout the project as a result of the large amount of data that has been worked with.
 - **Python**Used for the study of Pickup points or Dropoff points of taxis that may be in the water and for the construction of the model.


## Data acquisition

1. The Taxi Trips dataset was provided by Chicago Data Portal [here](https://data.cityofchicago.org/Transportation/Taxi-Trips/wrvz-psew) and consists in a `csv` file with *112.860.054 rows*, *24 columns* and *45,75 GB*.

	- A codebook of the data set is available [here](Information/CodeBookTaxiTrips.pdf).

2. The Weather dataset was provided by Kaggle [here](https://www.kaggle.com/selfishgene/historical-hourly-weather-data) and consists of a folder with 7 CSVs referring to different cities of USA, Canada and Israel, which have data referring to:

	1. City Attributes
	2. Humidity
	3. Pressure
	4. Temperature
	5. Weather Description
	6. Wind Direction
	7. Wind Speed

3. We have obtained from [here](https://www.openstreetmap.org/export#map=10/41.8453/-87.7400) a map of the city of Chicago which will be used to eliminate those points that are in the water. With the help of Adobe Photoshop the color of the water has been highlighted, darkening in turn the color of the earth.

4. We have also created an Excel file with translation of the referent fields Pickup Community Area and Dropoff Community Area [here](Information/Community_Areas_and_Neigborhoods_City_of_Chicago.xlsx).

All this information can be downloaded by running the notebook: [`download_files_drive.ipynb`](Scripts/download_files_drive.ipynb) 


## Exploratory data analysis (EDA)

### Description
The main tasks during this phase were transforming data, dealing with missing values,filter outliers and strange values and visualizing raw data by plotting frequency.

### Notebooks used
In this phase, several notebooks have been used, being these the following ones:

#### Notebooks used for the analysis and treatment of the Chicago Taxi Trips dataset:

1. [`exploratory_taxi_data.ipynb`](Scripts/exploratory_taxi_data.ipynb): In this notebook with the help of **PySpark** what has been done is to perform a first analysis of the dataset of taxi journeys following the next steps: 
		
	1. We have carried out a transformation of the names of the fields to comply with good practices.
	2. We have converted the dates to date format.
	3. We have analyzed the most repeated values in each of the axes.
	4. We have eliminated the useless columns
 	5. Finally we have analyzed the values null and strange making a count of how many trips would remain after this first analysis.
	
2. [`filtering_taxi_trip_data.ipynb`](Scripts/filtering_taxi_trip_data.ipynb): In this notebook what has been done has been based on the analysis carried out in the previous notebook to carry out the erasure of the useless axes, the change of name of the columns, the change of format of the date fields, the filtering of the trips with strange values and the elimination of the trips with null values and finally it has been saved in a new CSV (A separate notebook has been used for the whole process of the first notebook to be able to perform the filtering without running the previous notebook).
	
3. [`delete_location_water.ipynb`](Scripts/delete_location_water.ipynb): In this notebook what has been done is to represent in the map of Chicago the Pickup and Dropoff points of the remaining trips of the filtering carried out in the previous notebook. The idea is all those trips that have the point of departure or arrival in the water eliminate them. 
	
	After carrying out this analysis have been found a residual number of departure or arrival points in the water so it has been decided not to eliminate them.

#### Notebooks used for the analysis and treatment of the Chicago Weather:

1. [`exploratory_filtering_chicago_weather_data.ipynb`](Scripts/exploratory_filtering_chicago_weather_data.ipynb): In this notebook what we do is read 6 of the 7 downloaded files (City Attributes we don't use it), keep the information about Chicago and do an exploration of the data.

#### Notebooks used for the analysis, treatment and union of the Taxi Trips and Weather datasets resulting from the previous processing:

1. [`final_eda.ipynb`](Scripts/final_eda.ipynb): In this last notebook before entering the modeling, what has been done is to join the datasets of Chicago Taxis and Chicago time generated in previous notebooks, to later make a more exhaustive analysis which has allowed us to make a deeper filtering.

	Once this has been done, we have taken a visualization of the data, an analysis of the variables that most influence the price of the taxi to finally create the datasets with which to carry out the modeling and visualization.



		

