# EDA description
Explore Blue Ocean Gear’s buoy data using Jupyter notebooks. Our main goals in this milestone are to: 
(1) clean the dataset by identifying and removing invalid data points; 
(2) calculate buoys’ average range of motion by fishery; 
(3) contextualize buoy movement by documenting known traits (e.g., wave and current patterns) of the surrounding water bodies; 
(4) investigate potential breakaway events; and 
(5) describe how buoys’ reported metrics, like battery temperature, water temperature, and salinity, vary across time and space.  

These tasks will help us prepare, and develop an intuition for, the dataset ahead of predictive modeling.

# Research Question
## Buoy Message Analysis
Total Number of Messages: How many unique buoys are in the dataset? Messages?


Data Fields:  List the message dataset fields/columns. Do any strong negative or positive correlations exist between fields? Produce a correlation matrix as a visualization. Are there fields/columns that contain null, dummy, or missing values?


Analyze Messages by Buoy: How are messages distributed across buoys? Did some buoys transmit many more messages than others? Produce a graph (e.g., bar plot, histogram, box-and-whisker plot) to visualize this.


Analyze Messages over Time: What is the date range of the buoy messages? How are messages spread across time?  Are they concentrated in a particular week or month, or fairly spread out?


Analyze Messages by Geography: What is the geographic distribution of messages (i.e., what are the geographic coordinates of a “bounding box” that would contain all buoys)?  Are any outside the expected territory? To visualize this, produce an interactive map with all of the messages plotted as points as well as a rectangular bounding box representing the min and max coordinates.
 
Analyze Messages by Fishery: Each message occurs within a given fishery (e.g., lobster, crab). Which buoys were present in each fishery? How many messages occurred within each fishery? What was the date range of messages for each fishery?  Update the map to color-code messages by fishery (include a legend).


Label Messages with Buoy Deployment Identifiers: A buoy “deployment” begins when it enters the water (as indicated by an “Entered Water” status) and ends when it leaves the water (“Left Water”). Assign each buoy message a deployment id that represents the deployment that it was a part of. How many deployments occurred? How many times was each buoy deployed? How long did each deployment last?  How many messages are in each deployment (i.e. how long is each time series)?


Drop Bad Data: Drop any errant messages that (a) occur outside the expected geographic zone and/or (b) are the only message in their deployment. If applicable, document which messages were dropped and why.
 
Repeat the Analysis using Clean Data: Repeat the analysis above–“Total Number of Messages”, “Data Fields”, “Messages by Buoy”, “Messages over Time”, “Messages by Geography”, and “Messages by Fishery”, and “Buoy Deployments”–with the clean dataset.

## Preliminary Buoy Motion Analysis
Calculate Buoy Deployments’ Smallest Enclosing Circles: For each buoy deployment, generate the smallest circle that encloses all of the plotted messages in that deployment. Caution: The smallest circle algorithm uses Euclidean distance, while GPS coordinates are typically given in ellipsoidal coordinates. You will have to determine the best way to convert between them. A previous attempt used the Universal Transverse Mercator (UTM) projection, which casts the Earth to a grid in which each cell is a flat surface permitting Euclidean distance calculations. This may be viable for the dataset, but accuracy drops if buoy deployments occur across multiple UTM zones. 
 
Analyze Buoys’ Range of Motion: Calculate the radius of each enclosing circle. Then examine the distribution of radii across deployments. On average, what is the radius size?  Are there any outliers? How do the radii differ by fishery? Does the radii change over time, all else being equal?  Plot some histograms for visualization. Then graph each buoy deployment and its enclosing circle on a map. If there are many deployments, save the maps as images in a separate directory. Color code the buoys by their velocity.


Trace Outliers: Investigate any buoys that have large ranges of motion. Are there any suspected cases of a buoy breaking off from its gear or being dragged by a boat or  an animal?  Describe how those buoys traveled, when the anomalous behavior started, and how their velocity and acceleration changed during that period (as well as any other relevant conditions provided by the dataset). Visualizations would be helpful. (NOTE: One way to pinpoint the start of the “anomaly” is by measuring how much larger the radius of the smallest enclosing circle would grow after that point was included. Be creative and see if you can come up with a better strategy!)
 
Analyze Buoy Depth: For each deployment, determine the range of depth.  Did any buoys submerge underwater? If so, how deep did they go, how many times did they dive, and how long were they under? Do these submerging events correspond to the anomalous surface motion behavior?
 
Describe Buoy Motion per Fishery: For each fishery, determine the median range of motion/smallest circle radius as well as the depth.