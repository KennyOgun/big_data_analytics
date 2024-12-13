# Bike Ride Data Analysis

The primary objective of this analysis is to explore the hypothesis suggesting that **Rides originating from Baylis Road, Waterloo Station in 2014 were shorter compared to rides originating from alternative stations** using Big Data-Apache Spark

# Exploratory Data Analysis (EDA)

The London bike rides dataset consisted of twenty CSV files, each containing monthly data rides with varying row counts. The files were inspected  to identify the informative schemas. Only nine schemas were found to be informative, while others were not useful.

**Most Informative Schemas:**

**Rental Id:** A string of figures for rental identification purposes.

**Duration:** The duration of the rides in seconds.

**Bike Id:** Used for bike identification.

**End Date:** The end date of a bike ride.

**EndStation Id:** The ID of the end station.

**EndStation Name:** The name of the end station.

**Start Date:** The start date of the bike ride.

**StartStation Id:** The ID of the start station.

**StartStation Name:** The name of the start station.

**Non-Informative Schemas:** c9 , c10 , c11 .These non-informative schemas contain blank information and will be removed from the dataset.

# Data Cleaning

All the data files were merged to consolidate their information, resulting in a total row count of 11,249,221.
 
1. Missing Values: Missing values varies across the schemas ranging from 1,239,113 to 1,239,242 rows, these were removed.
 
3. Negative and Zero Values: There are presence of negative values(149 rows) and zero values (31,510 rows) in the Duration columns that were removed.
   
4. Non-relevant years:  Count of 2013 data of 316,799 rows and 2015 data of 30,272 rows were identified as outliers in the dataset.

5. No duplicates were identified

**The resulting cleaned dataset contains 9,632,758 rows, meaning  a tiny fraction, about 1%, of our original data was lost.**

**Variables Required for Analysis**

To answer the research hypothesis, the following variables are  necessary from the schemas:

**Duration:** Represents the total duration of bike rides, formatted as an integer in seconds.

**Start Date:** This schema contains the month and the year needed for the  average duration analysis.

**Start Station Name:** "Baylis Road, Waterloo Station" will be derived specifically from this schema.


**Data Suitability and Splitting for Comparative Analysis**

The dataset was divided into two data frames for comparative analysis: one for **Baylis Road, Waterloo**, and one for **other stations**. 

This approach is logical because the hypothesis focuses on rides from Baylis Road, Waterloo. Therefore, it was necessary to separate this station's data from the rest, combining the other stations into a single data frame labeled 'other stations' for comparison.

1. **Baylis Road, Waterloo: Data Information**

The Baylis Road, Waterloo data frame contains 25,703 rows, which is approximately 0.27% of the total dataset.
The minimum and maximum ride durations are 1 hour and 10,470 hours, respectively.

3. **Other Stations: Data Information**
   
The data frame for other stations contains 9,607,055 rows, about 99.73% of the total dataset.
The minimum and maximum ride durations are 1 hour and 43,276 hours, respectively.

# HYPOTHESIS TESTING

The  hypothesis testing are:

**Null Hypothesis (H0):**

The average ride durations from Baylis Road, Waterloo are equal to the average ride durations from other stations. In other words, there is no significant difference in the average ride durations between Baylis Road, Waterloo and other stations.

**Alternative Hypothesis (H1):** 

The average ride durations from Baylis Road, Waterloo are different from the average ride durations from other stations. In other words, there is a significant difference in the average ride durations between Baylis Road, Waterloo and other stations.

**T-TEST**

In this section, a t-test was performed to determine which of the hypotheses can be confirmed. My assumptions are stated below;

Assumptions for T-Test: 
1.The samples are independent: By design, the samples are collected independently. This assumption is generally satisfied if the data was collected in such a manner.
2.The data follows a normal distribution:The data follows a normal distribution. Histograms and Q-Q plots are used to visually assess normality.
3.Alpha Level:A significance level of p = 0.05 was assumed. If p > 0.05,  reject H0, indicating significant differences in ride durations.
4.The variances of the two populations are equal (homogeneity of variance).

<img width="245" alt="image" src="https://github.com/user-attachments/assets/efd80c6e-9485-4fae-8729-6a638ad67a42" />

Comment: The KDE curve resembles a bell curve, it indicates normality.

<img width="244" alt="image" src="https://github.com/user-attachments/assets/3a3768af-992a-4b28-8398-7fb2f44dff45" />

**Comments: The p-value (2.7363) > 0.05.Null hypothesis rejected.**

**Results:*8

**Accepted Hypothesis:Alternative Hypothesis (H1):**

**There is significant difference in ride durations between Baylis Road, Waterloo and other stations in 2014. In other words, the average ride duration for rides originating from Baylis Road, Waterloo Station were indeed shorter compared to rides originating from other stations.  Specifically, the average ride duration for Baylis Road, Waterloo Station is about 7 hours shorter from the Other stations.**

