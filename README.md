# Project Overview
This project uses world wide earthquakes event data from the United States Geological Survey (USGS). 
Python and Spark are used to fetch and process the USGS API data [https://earthquake.usgs.gov/fdsnws/event/1/#parameters]. Once fetched, the data is processed incrementally using a medallion architecture consisting of three layer: bronze, silver and gold. Then, using Data Factiry, a data pipeline is created to dynamically define the start date and end date parameters that are needed in the url for the API call, and the updated datesets that will be created by schedulling daily API calls to update the data. Finally, a Power BI report shows the map visual of the earthquakes.

![alt text](https://github.com/Micaeka1/MS-Fabric-Earthquake-Project/blob/main/Images/Steps%20Overview.png)

# Bronze Layer
In this stage of the architecture, raw data is ingested into the lakehouse via API calls. The start and end date parameters are defined in the Data Factory stage.

![alt text](https://github.com/Micaeka1/MS-Fabric-Earthquake-Project/blob/main/Images/Bronze%20layer.png)

[See 01 Worldwide Earthquake Events API - Bronze Layer Processing.ipynb for full code used in this layer]

# Silver Layer
Data cleanup and validation are performed in this layer. 

Here we:

- Extract properties like 'time', 'update', 'mag' into their own dedicated columns
- Convert the 'time' and 'update' columns from millisecond to datetime format.
- Extract the coordinates into separate longitute, latitude and elevation columns.

![alt text](https://github.com/Micaeka1/MS-Fabric-Earthquake-Project/blob/main/Images/Silver%20Layer.png)

[See 02 Worldwide Earthquake Events API - Silver Layer Processing.ipynb for full code used in this layer]

# Gold Layer
The dataset is further optimised for business use.


# Data Factory

- **Bronze Layer:** 
# Power BI Report

![alt text](https://github.com/Micaeka1/MS-Fabric-Earthquake-Project/blob/main/Images/Earthquake%20visual.png)
[View update map here](https://app.powerbi.com/view?r=eyJrIjoiYTVlZWM3ZGYtMGNmYy00ZDMyLWJmM2MtOWVkN2ExZjMwNDY1IiwidCI6ImI0YmU2ZWM5LWUxZjYtNDFhYy04Mjk3LWMyYzliODRlMTgxOCJ9&embedImagePlaceholder=true)
