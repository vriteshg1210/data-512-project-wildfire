# data-512-project-wildfire

# Overview

This work is inspired by the project which we were assigned to work on in DATA 512. This is Part 1 of the analysis on wildfires and how the smoke from wildfires affects the cities near them. I have been assigned to Klamath Falls, Oregon. The main inspiration behind this project is that more frequently summers in the western US have been characterized by wildfires with smoke billowing across multiple western states. There are many proposed causes for this: climate change, US Forestry policy, and growing awareness, just to name a few. Regardless of the cause, the impact of wildland fires is widespread.

# Datasets

1) A geojson file dataset collected and aggregated by the US Geological Survey. This contains fire polygons for wildfires that have occurred across the USA. The file can be found here- https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81
2) An API accessing sample notebook to obtain the Air Quality Estimates for regions in the USA- https://drive.google.com/file/d/1bxl9qrb_52RocKNGfbZ5znHVqFDMkUzf/view?usp=sharing
3) A spreadsheet listing the assignments of different cities- https://docs.google.com/spreadsheets/d/1cmTW5fgU3KyH6JbrRao-qWjzu2GovKk_BkA7a-poGFw/edit#gid=1247370552
   
# Licensing

1) Creative Commons License: https://creativecommons.org/licenses/by/4.0/
2) This project is open-source and follows the MIT License. You are free to use and modify the code according to the terms of the MIT License.
   
# Important Considerations for the Data

The GeoJSON dataset provided by the USGS is extensive, encompassing around 136,000 fire occurrences that demanded comprehensive analysis. While utilizing Prof. David McDonald's Reader facilitated data loading, filtering this dataset involved the meticulous selection of fire occurrences relevant to the scope of this assignment, a task that consumed a substantial amount of time.

Additionally, extensive error handling was essential since not all fields were consistently present in every data row. An example of this is the 'rings' parameter, which required careful validation and appropriate handling.

It's worth noting that data is accessible for all years except 2021, 2022, and 2023 for analysis purposes.

Working with AQI data posed its unique challenges. In the case of our study city, Lewiston, Idaho, no monitoring stations are located within the city or within a 25-mile radius. The closest station is situated 50 miles away. Furthermore, there's no single station with complete data for all the analysis years, necessitating data aggregation from multiple station responses.

Because different weather stations operated in different years, data consolidation was mandatory across these two distinct stations.

Moreover, responses from the EPA API sometimes lack the 'aqi' parameter, requiring robust exception handling. In my city locations, data for gaseous pollutants was notably absent, with only data available for particulate pollutants, prompting the need for specialized handling in this specific scenario.

# Dependencies
Python 3 Jupyter Pandas Requests

# Helpful Documentation
This project adheres to the recommended best practices for replication and documentation:

Jupyter Notebook: detailed comments for data acquisition, processing, and analysis.

README File: Offers a general overview of the project, outlining its objectives, data sources, data processing procedures, and standards for reproducibility.

LICENSE File: Contains the MIT LICENSE for the project's code, ensuring it is freely usable and the Creative Commons License.

# Code
1) I have this ipynb notebook for data acquisition and analysis: DATA 512 Wildfire Part 1.ipynb
2) There is another ipynb for the acquisition of AQI data- epa_air_quality_history.ipynb

# Data Files
1) USGS_Wildland_Fire_Combined_Dataset.json- The file having all the wildfire data
2) aqi_list.json- The file having AQI data for Klamath Falls

# Procedure to replicate this project

Step 1: Data Acquisition
Obtain the Wildfire and AQI data by collecting data from the specified sources and making API calls to gather additional information required for analysis.

Step 2: Data Filtering for Scope
Filter the data acquired in Step 1 to include only wildfires that occurred within a 1250-mile radius from the source city and within the years 1963-2023.

Step 3: Smoke Estimate Calculation
Calculate the smoke estimate using attributes from the filtered wildfire data.

Step 4: Time Series Forecasting and Prediction
Utilize time series forecasting techniques to predict smoke levels for future dates in the city of interest based on the smoke estimates from Step 3.

Step 5: Visualization and Analysis
Perform visualizations and analyses as prompted by the instructor:
- Create a histogram showing the number of fires at 50-mile intervals up to the specified maximum distance from your assigned city.
- Generate a time series graph displaying the total acres burned per year for fires within the specified distance from your city.
- Create a time series graph presenting both the fire smoke estimate and AQI estimate for your city.

These steps outline the key phases of Data Acquisition, Data Preparation, and Data Analysis within the project.
A much more detailed step-by-step procedure to reproduce this project is given in the notebook attached to this repository.

# Research Implications
An initial analysis has been done to study the nature of the impact of wildfires on the AQI of the city near it. Further research will be done in the following parts.

# Important Links
1) https://www.sciencebase.gov/catalog/file/get/61aa537dd34eb622f699df81?f=__disk__d0%2F63%2F53%2Fd063532049be8e1bc83d1d3047b4df1a5cb56f15&transform=1&allowOpen=true
2) https://aqs.epa.gov/aqsweb/documents/data_api.html
3) https://www.statsmodels.org/stable/generated/statsmodels.tsa.ar_model.AutoReg.html
4) https://drive.google.com/file/d/1qNI6hji8CvDeBsnLDAhJXvaqf2gcg8UV/view

# Contact Information
For any additional questions or feedback, please contact [Vritesh Gera] at [vriteshg@uw.edu]
