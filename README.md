# Machine Learning-Based Method for Earthquake Analysis in Japan: A Preliminary Study
In Japan, earthquakes frequently occur and cause devastating damage to human lives and infrastructure. This preliminary study aims to analyze earthquake data in Japan and utilize a machine learning method to predict the magnitude and depth of earthquake based on the earthquake location and timestamp. 

We visualized data in three parts: locations of earthquakes, the relationship between the number of occurrences and time, and the relationship between the number of occurrences and magnitude (Gutenberg-Richter Law). 

We then split data into the train set and the test set (80:20) in the Relative Intensity model, and into the train set, the test set, and the validation set (80:10:10) in the machine learning model. We use Relative Intensity (RI), receiver operating characteristic (ROC), and Pierce’s skill score to find the locations with high risk for earthquake occurrences. Then, we use the machine learning-based model to find the relationship between time, locations, magnitude, and depth.

The result demonstrated that earthquakes in Japan can be explained using both conventional and proposed models. Also, while both of our models have their advantages and drawbacks, they can analyze the data to a certain extent.

## Introduction
In Japan, earthquakes frequently occur and cause devastating damage to infrastructure and human lives. For example, in 2000, there was a large-scaled earthquake which occurred in Tottori prefecture, Japan. About $150 million in damage was caused (with 104 buildings destroyed) and between 130-182 people were injured. This shows the importance of analyzing earthquake data.

By using both relative intensity (conventional) and machine learning-based method, this preliminary study aims to utilize various method to analyze earthquake data in Japan. We also aim to prove the validity for machine learning method in earthquake analysis. 

## Framework
### Part 1: Data Format and Data Visualization
In this study, an earthquake dataset, which contains the time, locations, magnitude, and depth of each earthquake in Japan from 1985-2022, was obtained from Japan Meteorological Agency. 

We first converted the date and time to the timestamp for better usability. To further understand the dataset, we then visualized these data in 3 ways. 
1.	Locations of earthquake occurrences
2.	The relationship between the number of occurrences and time
3.	The relationship between the number of occurrences and magnitude (Gutenberg-Richter Law) is then also used to find the Gutenberg-Richter relationship in earthquakes. We calculated the logarithm base 10 of occurrences and approximate the relationship using linear regression.

Then, we split the data for training each model. For the Relative Intensity Method (Conventional), we divided 70% of the data into the train set and 30% into the test set (time-sequential). For neural network, we normalized these data. Then, we separated data into X (timestamp, latitude, longitude) and Y (magnitude, depth). After that, we divided 80% of the data into the train set, 10% of the data into the test set, and 10% of the data into the validation set at random state=42.

### Part 2: Relative Intensity Method (Conventional)
The RI model measures past seismic activities in areas and is used to determine the potential for a new earthquake. We then define the study area (ranges from 30°N 128°E to 46°N 146°E) as a point with even spacing. The RI score, an index (ranges from 0 to 1) used in the RI method, is a min-max normalized Cumulative Benioff Strain of a point in the study area. The formula for Cumulative Benioff Strain at a time B_{xy}(t) is as follows.
