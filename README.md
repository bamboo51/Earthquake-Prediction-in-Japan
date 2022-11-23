# Machine Learning-Based Method for Earthquake Analysis in Japan: A Preliminary Study
In Japan, earthquakes frequently occur and cause devastating damage to human lives and infrastructure. This preliminary study aims to analyze earthquake data in Japan and utilize a machine learning method to predict the magnitude and depth of earthquake based on the earthquake location and timestamp. 

We visualized data in three parts: locations of earthquakes, the relationship between the number of occurrences and time, and the relationship between the number of occurrences and magnitude (Gutenberg-Richter Law). 

We then split data into the train set and the test set (80:20) in the Relative Intensity model, and into the train set, the test set, and the validation set (80:10:10) in the machine learning model. We use Relative Intensity (RI), receiver operating characteristic (ROC), and Pierce’s skill score to find the locations with high risk for earthquake occurrences. Then, we use the machine learning-based model to find the relationship between time, locations, magnitude, and depth.

The result demonstrated that earthquakes in Japan can be explained using both conventional and proposed models. Also, while both of our models have their advantages and drawbacks, they can analyze the data to a certain extent.

# Introduction
In Japan, earthquakes frequently occur and cause devastating damage to infrastructure and human lives. For example, in 2000, there was a large-scaled earthquake which occurred in Tottori prefecture, Japan. About $150 million in damage was caused (with 104 buildings destroyed) and between 130-182 people were injured. This shows the importance of analyzing earthquake data.

By using both relative intensity (conventional) and machine learning-based method, this preliminary study aims to utilize various method to analyze earthquake data in Japan. We also aim to prove the validity for machine learning method in earthquake analysis. 

## Framework
