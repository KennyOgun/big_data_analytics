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

**Data Cleaning**

1. All the data files were merged to consolidate their information, resulting in a total row count of 11,249,221.
 
2. Missing Values: Missing values varies across the schemas ranging from 1,239,113 to 1,239,242 rows.
 
3. Negative Values: There are presence of negative values in the Duration columns.
   
4. Start and End Station count: Unique count of End Stations is 766 while that of Start Stations is 764

**Variables Required for Analysis**

To answer the research hypothesis, the following variables are  necessary from the schemas:

**Duration:** Represents the total duration of bike rides, formatted as an integer in seconds.

**Start Date:** This schema contains the month and the year needed for the  average duration analysis.

**Start Station Name:** "Baylis Road, Waterloo Station" will be derived specifically from this schema.

**The resulting cleaned dataset contains 9,632,758 rows, meaning  a tiny fraction, about 1%, of our original data was lost.**

