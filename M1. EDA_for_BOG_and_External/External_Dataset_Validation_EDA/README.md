# EDA for External Dataset Analysis 

## Objective
Explore open source ocean current and temperature datasets that will be used in future modeling tasks. Our main goals in this milestone are to: (1) describe oceanographic patterns over time and space,
(2) write scripts that can easily collect data from satellites and in situ measuring devices, 
(3) explore relationships between Blue Ocean Gear (BOG) buoys’ motion and reported temperatures with those from the external datasets, and 
(4) note anomalies in BOG buoy temperatures.

### Analysis of Copernicus Satellite Data

1. Analyze Geography: What is known about the water bodies the Blue Ocean Gear buoys are traveling in?  Before fetching global temperature and ocean surface current data from Copernicus, describe their bathymetry, temperature, tidal, and/or wave patterns and cite your source(s).

2. Retrieve Copernicus Data.  Write a Python script that downloads data from the Copernicus API in NetCDF form.  Your script should take a bounding box, datetime range, and variable name as input and return data within that time frame and geographic region. Update (10/8): You can refer to the example notebook for help getting started.
 
3. Visualize Copernicus Data.  Plot each variable (sea surface current direction and temperature) on top of a map at different timestamps to illustrate how the variable changes over time in the Northwest Atlantic.
 
Analyze Buoy Water Temperature: Segment the buoy messages into deployments based on their “Entered Water” and “Left Water'' flags. Then plot the deployment groups’ water temperature over time and space and describe any patterns.
 
4. Merge Copernicus and Buoy Data.  Load the Blue Ocean Gear buoy message data and plot the message locations on a map, on top of the satellite data, at a given timestamp. Draw buffers (circles) around each buoy location and then calculate the min, max, and average of the satellite data within the buffers.  Repeat this for every timestamp corresponding to the buoys. This should result in a DataFrame that contains the timestamp; buoy latitude, longitude, and temperature; and the min, max, and average temperature of the satellite data within the buffer.
 
5. Compare Temperature Measurement Series.   For each buoy deployment, calculate the difference between the buoy reported temperatures and Copernicus’ reported temperatures.  Are those differences significant?

### Analysis of Nearest Weather Station Data
1. Analyze Geography: What is known about the water bodies the Blue Ocean Gear buoys are traveling in?  Before fetching global temperature and ocean surface current data from Copernicus, describe their bathymetry, temperature, tidal, and/or wave patterns and cite your source(s).

2. Retrieve Station Data.  Write a Python script that downloads buoy weather station data from Environment and Climate Change Canada’s ERDDAP server as a CSV given a date range and a list of variables. We’ll want to download sea surface temperature data from both DFO MEDS and ECCC MSC. Update (10/8): You can refer to the example notebook for help getting started.
 
3. Visualize Data.  Create maps and/or plots to visualize how sea surface temperature varies over time for different stations.
 
4. Analyze Buoy Water Temperature: Segment the buoy messages into deployments based on their “Entered Water” and “Left Water'' flags. Then plot the deployment groups’ water temperature over time and space and describe any patterns.
 
5. Merge Copernicus and Buoy Data.  Load the Blue Ocean Gear buoy message data and plot the message locations on a map with the weather station points, at a given timestamp. For each timestep, calculate each message’s nearest weather station and record what the temperature is. This should result in a DataFrame that contains the timestamp; buoy latitude, longitude, and temperature; and the sea surface temperature of the nearest weather station.
 
6. Compare Temperature Measurement Series.   For each buoy deployment, calculate the difference between the buoy reported temperatures and the stations’ reported temperatures.  Are those differences significant?
