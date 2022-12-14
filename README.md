# Ocean Gear Anomaly Detection

## Project Context
Blue Ocean Gear currently maintains a customer web portal that reports Smart Buoy data (e.g., location, sea surface temperature and salinity, velocity) in near real-time. 
Locating lost buoys and fishing gear remains a pain point.  In the next iteration of the platform, BOG hopes to provide customers with predicted buoy locations and detected location anomalies in order to recover lost gear and inspect suspect gear more quickly.
BOG would also like to validate its buoys’ measurement readings against those from external sources to ensure accuracy and gauge if the readings could, in the future, be used as a service for monitoring local environment conditions.

## Project Objective
To build a well-documented and well-tested machine learning (ML) pipeline that generates reports of buoy activity in “near real-time” to answer these four questions:
Where will a Smart Buoy move next when attached to fishing gear?
Does a given movement of a Smart Buoy represent an anomaly?
Where will a Smart Buoy that has broken off its gear “drift”/travel?
How do Smart Buoys’ sensor readings compare to readings from external data sources? Are there any systematic errors or anomalies?

## Dataset
1. Smart Buoy readings
-New Brunswick(single-line pots for snow crab)
-Massachusetts(long-line hooks for swordfish)
-Maine(single-line pots for lobster)
2. Free and open-source ocean data from satellites, weather stations, other drifting buoys, and/or high-frequency radar stations

## Milestones
### M1. Exploratory Data Analysis
1. Describe buoy motion, temperature, and salinity by fishery, before modeling
2. Describe geographical patterns in ocean current, temperature and salinity
3. Assess whether buoy measurement series significantly differ from external sources and/or contain anomalies (e.g., spikes)

4. Outcomes
-Jupyter notebook(s) that can be executed by the client
-Python scripts for collecting data and generating plots and visualizations
-Client presentation summarizing results

### M2.Location Prediction – Secured Buoys
1. Start with the heuristic (smallest enclosing circle) developed during EDA as a baseline
2. Run hundreds of thousands of simulations of secured buoys in the North Atlantic using OceanParcels
3. Use simulation data to train random forests (RF), long short-term memory neural networks (LSTM), and/or transformers and then fine-tune models on actual BOG buoy trajectories
4. Evaluate and compare model results
5. Outcomes
-Jupyter notebook(s) demonstrating and comparing different approaches
-Python scripts for running simulations and models
-Client presentation summarizing progress and results

### M3.Location Prediction – Drifting Buoys
1. Run hundreds of thousands of simulations of drifter motion in the North Atlantic using OceanParcels
2. Pre-train different deep learning models (e.g., transformers, LSTMs) on this synthetic data and then fine-tune it on actual drifter trajectories collected from external data sources
3. Generate prediction intervals where a drifting buoy may be located
4. Test the model on actual cases of BOG drifting buoys
5. Outcomes
-Jupyter notebook(s) demonstrating and comparing different approaches
-Python scripts for running simulations and models
-Client presentations summarizing progress and results
