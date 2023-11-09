# Common Analysis - DATA512

# AIM

The goal of this project is to analyze wildfire impacts on a specific city in the US. The end goal is to be able to inform policy makers, city managers, city councils, or other civic institutions, to make an informed plan for how they could or whether they should make plans to mitigate future impacts from wildfires.

# Folder Hierarchy

├── <b>Data/</b><br>
&nbsp;&nbsp;&nbsp;├── Smoke_Estimate_Annual.csv<br>
&nbsp;&nbsp;&nbsp;├── aqi_yoy.csv<br>
&nbsp;&nbsp;&nbsp;├── aqi_gaseous.csv<br>
&nbsp;&nbsp;&nbsp;├── aqi_particulate.csv<br>
├── <b>Code/</b><br>
&nbsp;&nbsp;&nbsp;├── Data_Extraction_Analysis.ipynb<br>
&nbsp;&nbsp;&nbsp;├── Reader.py<br>
&nbsp;&nbsp;&nbsp;├── Wildfire_short_sample.json<br>
&nbsp;&nbsp;&nbsp;├── __init__.py<br>
&nbsp;&nbsp;&nbsp;├── test_geocalc.py<br>
├── <b>Output/</b><br>
&nbsp;&nbsp;&nbsp;├── Visualization_1.png<br>
&nbsp;&nbsp;&nbsp;├── Visualization_2.png<br>
&nbsp;&nbsp;&nbsp;├── Visualization_3.png<br>
&nbsp;&nbsp;&nbsp;├── Validation_Forecast.png<br>
&nbsp;&nbsp;&nbsp;├── Test_Forecast.png<br>

# Prerequisites
Before using this code, ensure you have the following prerequisites installed:

1.) Python 3

2.) Requests

3.) Pandas

# Data Sources and Description

USGS_Wildland_Fire_Combined_Dataset.json: This contains the Combined wildland fire datasets for the United States and certain territories [Link](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) 

US City assigned for individual analysis -  [Google spreadsheet](https://docs.google.com/spreadsheets/d/1cmTW5fgU3KyH6JbrRao-qWjzu2GovKk_BkA7a-poGFw/edit)

The city under consideration for my analysis is Derby, Kansas with coordinates (37.552407, -97.261492)

# Licenses and Reference Code

This project is licensed under the MIT License. The sample codes shared for reference have been provided under the [Creative Commons CC-BY license](https://creativecommons.org/licenses/by/4.0/):

[Sample Code for GeoJSON reader](https://drive.google.com/file/d/1TwCkvdaw0MxJzW7NSDg6XxYQ0dvaS44I/view)

[Sample Code for Distance Computation](https://drive.google.com/file/d/1qNI6hji8CvDeBsnLDAhJXvaqf2gcg8UV/view)

[Sample Code for fetching data from US EPA Air Quality System API](https://drive.google.com/file/d/1bxl9qrb_52RocKNGfbZ5znHVqFDMkUzf/view)


# Reproducibility

The following steps need to followed to run this code seamlessly :

&emsp; Clone this repository to your local machine.<br>

&emsp; Install all the required libraries.<br>

&emsp; Download the jsons - USGS_Wildland_Fire_Combined_Dataset.json and USGS_Wildland_Fire_Merged_Dataset.json from  the following [link](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) by downloading the GeoJSON Files.zip folder and store these two jsons into the Data Folder<br>

&emsp; Run Data_Extraction_Analysis.ipynb to generate all Visualizations and output csv file stored in Data Folder<br>


# Considerations for Analysis and Reproducibility

&emsp; The input data file needs to be downloaded from the link mentioned under Data Sources and should be kept in the Data Folder for successful Execution of the Python Code<br>

&emsp; The Json Files created in the code are not present under the Data Folder due to its large size and hence need to be stored in the data folder before running the code<br>

&emsp; The distance threshold from the city assigned has been kept at 1250 miles for the time period between 1963 - 2023<br>

&emsp; The data is not well distributed and hence fires over the entire year have been considered instead of the fires between 1st May to 31st October.<br>

&emsp; A modified version of ARIMA called SARIMA has been used in forecasting the Smoke Estimate for the next 25 years (2024-2049)<br>

&emsp; Because of the large size of the "USGS_Wildland_Fire_Combined_Dataset.json" file it could not be uploaded on GitHub. Therefore to reproduce the results it is imperative to download the GeoJSON Files.zip from this link and extract the "USGS_Wildland_Fire_Combined_Dataset.json" file and place it under the data folder.
The "all_fire_data_with_distance.csv" file is not present under the intermediate data folder because of its large size. However, if one follows the steps mentioned below to reproduce the analysis, it will be generated and no manual intervention is required.




# Output

Visualization 1 : Produce a histogram showing the number of fires occurring every 50 mile distance from your assigned city up to the max specified distance.

![image](./Output/Visualization1.png)

Visualization 2 : Produce a time series graph of total acres burned per year for the fires occurring in the specified distance from your city.

![image](./Output/Visualization2.png)

Visualization 3 : Produce a time series graph containing your fire smoke estimate for your city and the AQI estimate for your city.

![image](./Output/Visualization3.png)

Validation Forecast : 

![image](./Output/Validation_Forecast.png)

Test Forecast : Census divisions by total coverage: A rank ordered list of US census divisions (in descending order) by total articles per capita

![image](./Output/Test_Forecast.png)

# License

This assignment code is released under the MIT License.
