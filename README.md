
A Data Science project in Taxi Domain
===================
`#DataScience` `#PySpark` `#Python` `#MachineLearning` `#BigData` `#Spark` `#Taxi` `#Fare`


## Objetive ##

The main objective of this project is to try to predict the price that a taxi will cost us in Chicago based on the data of other trips made in this city and adding information about the weather. 

### About the methodology ###
The CRISP-DM (*cross-industry process for data mining*) methodology provides a structured approach to planning a data mining task and was applied to this data science project.

![CRISP-DM](Information/process.jpg)

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

All this information can be downloaded by running the notebook: [`download_files_drive.ipynb`](download_files_drive.ipynb) 
