# data_2_project
Code KY Data 2 Project
# Tesla Mapping Project - January/February 2023<br>
This project is intended to provide a place to merge data and modify datasets; and, visualize data from TeslaFi data logger that was exported as CSV files.<br>
<br>
The primary CSVs for this project are:<br>
-TeslaFi12023.csv<br>
-Teslafi22023.csv<br>
<br>
This project was was created in Visual Studio Code V1.75.1<br>
Required imports are:<br>
-import pandas as pd<br>
-import numpy as np<br>
-import matplotlib as mpl<br>
-import matplotlib.pyplot as plt<br>
-import statistics<br>
-from mpl_toolkits.basemap import Basemap<br>
-import matplotlib.pyplot as plt<br>
<br>
-a pip install of 'basemap' may be required, on your machine<br>
<br>
<br>
Feature of the product include:<br>
Feature 1: Loading Data in from the below TWO csv files:<br>
-Data read in from local CSV 'TeslaFi12023.csv'<br>
-Data read in from local CSV 'TeslaFi22023.csv'<br>
<br>
Feature 2: Clean and operate on the data while combining them.<br>
The data was merged with 'pd.concat'<br>
There are multiple cleanings of the data...<br>
-FIRST Cleaning: Dropping of columns that are not needed for this project, via 'df.drop()'<br>
-SECOND Cleaning: Data resampled to display data shown every 15 minutes, instead of the every minute shown by default export from TeslaFi.  This dataset was saved as the variable 'TF_resample'.<br>
-THIRD Cleaning: We still have a lot of data.  We filtered again to only show rows with a status of "online".<br>
<br>
-New Value: Data export only shows "passenger_temp_setting" in Celsius.  We have created a new column, converting to Fahrenheit.  New column name 'passenger_temp_settingF'.<br>
-New Value: We have divided battery range and maximum range columns and multiplied by 100 to give us the average percentage of maximum range used.  These results have been added as an additional column titled 'avg_percentage_used".<br>
<br>
Feature 3: Visualize/Present your Data.  Three visualizations are required.<br>
-ONE: Basemap of latitude/longitude points in January and February 2023<br>
-TWO: Zoomed in Basemap of latitude/longitude from January and February 2023.<br>
-THREE: Simple plot showing milage added to odometer from Jan 1 through Feb 28.  <br>
-FOUR: Simple scatter plot showing the outside temperature compared to the temperature set inside the vehicle<br>
<br>
<br>
Feature 4: Data Dictionary<br>
| Column Name | Description | Source | Optional |
| ----------- | ----------- | ------ | -------- |
| Date       | The date and time of data pulled | TeslaFi | N |
| state | State of vehicle (online/offline | TeslaFi | N |
| battery_range | Vehigle range, at battery charge | TeslaFi | N |
| charge_rate | Rate at which battery is charging, at that Date | TeslaFi | Y |
| longitude | Longitude of vehicle location | TeslaFi | N |
| latitude | Latitude of vehicle location | TeslaFi | N |
| speed | Vehicle speed at that Data | TeslaFi | Y |
| passenger_temp_setting | If dual climate active, passenget side temperature | TeslaFi | Y |
| is_auto_conditioning_on | Has user enabled climate control to prepare for drive | TeslaFi | Y |
| smart_preconditioning | Has vehicle enabled battery/electronics conditioning for preservation | TeslaFi | Y |
| fan_status | What speed is the climate control fan on | TeslaFi | Y |
| odometer | Vehicle odometer reading | TeslaFi | N |
| inside_tempF | Vehicle inside temperature | TeslaFi | N |
| driver_temp_settingF | Climate Control driver set temperature | TeslaFi | N |
| ouside_tempF | Environmental temperature at vehicle location | TeslaFi | N |
| maxRange | Maximum vehicle range | TeslaFi | N |
