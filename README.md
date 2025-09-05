# Project Overview
This project uses world wide earthquakes event data from the United States Geological Survey (USGS). 
Python and Spark are used to fetch and process the USGS API data [https://earthquake.usgs.gov/fdsnws/event/1/#parameters]. Once fetched, the data is processed incrementally using a medallion architecture consisting of three layer: bronze, silver and gold. Then, using Data Factiry, a data pipeline is created to dynamically define the start_date and end_date parameters that are needed in the url for the API call, and the updated datesets that will be created by schedulling daily API calls to update the data. Finally, a Power BI report shows the map visual of the earthquakes.

![alt text](https://github.com/Micaeka1/MS-Fabric-Earthquake-Project/blob/main/Images/Steps%20Overview.png)

# Bronze Layer
In this stage of the architecture, raw data is ingested into the lakehouse via the API calls.


[Entity Relationship Diagram here]

# Silver Layer
Data cleanup and validation are performed in this layer.

# Gold Layer
The dataset is further optimised for business use.

# Data Factory

- **Bronze Layer:** 
# Power BI Report

[ADD URL TO REPORT]

[[ADD IMAGE OF REPORT]](https://app.powerbi.com/view?r=eyJrIjoiYTVlZWM3ZGYtMGNmYy00ZDMyLWJmM2MtOWVkN2ExZjMwNDY1IiwidCI6ImI0YmU2ZWM5LWUxZjYtNDFhYy04Mjk3LWMyYzliODRlMTgxOCJ9&embedImagePlaceholder=true)
