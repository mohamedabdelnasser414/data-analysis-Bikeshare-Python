# data-analysis-Bikeshare-Python

# Introduction  
Bicycle-sharing systems have become increasingly popular in big cities, offering the public a convenient and flexible transportation option for short-distance trips. Among these systems is Divvy Bikes, serving Chicagoland by providing residents and visitors with an affordable and enjoyable way to explore and navigate Chicago and Evanston.

Divvy operates with a network of specially-designed, robust bikes that are securely docked at various stations throughout the region. Users can easily unlock a bike from one station and return it to any other station within the system. Becoming an Annual Member or purchasing a Pass through the Divvy station kiosk or the Divvy App grants individuals access to the service.

The versatility of bike share systems like Divvy makes them ideal for various purposes, including leisurely exploration, commuting to work or school, running errands, attending appointments, and engaging in social activities. Divvy remains accessible at all times, 24/7, 365 days a year, offering riders the freedom to use any bike and station within the extensive system.

For more information about Divvy Bikes, please visit their website at https://divvybikes.com/about. Embrace the joy of biking and experience the convenience of Divvy as you navigate through the bustling city of Chicago and beyond.

# Analysis Objectives

This project aims to analyze the Divvy trip data from the first quarter of 2019 to gain insights into city-wide biking trends. The following objectives will be addressed by answering the provided questions:

* Determine the total number of Divvy trips that occurred in the first quarter of 2019.
* Identify the number of bikes utilized during the first quarter of 2019.
* Determine which bikes were most frequently used for trips during this period.
* Calculate the average trip duration based on user types (e.g., customers and subscribers).
* Identify the most popular start stations from which Divvy trips were initiated.
* Identify the most popular end stations where Divvy trips concluded.
* Analyze and identify the most popular routes taken by Divvy Bikes users.
* Examine how Divvy Bikes usage is divided between customers and subscribers.
* Determine whether Divvy Bikes are used more by female or male users.
* Analyze the age distribution of Divvy Bikes users.
* Identify the peak times during which Divvy Bikes are most frequently used.
* Analyze Divvy Bikes usage patterns by day of the week.
By addressing these questions, we aim to gain comprehensive insights into the utilization patterns and preferences of Divvy Bikes users during the first quarter of 2019, which can provide valuable information for optimizing and enhancing the bike-sharing system's services and infrastructure.


# Dataset Description

The dataset contains historical trip data of Divvy Bikes and is available for public use. It was downloaded from the official Divvy Bikes website (https://divvybikes.com/system-data) and is released on a monthly schedule. The dataset is provided under the terms of the Divvy Data License Agreement.

File Name: Divvy_Trips_2019_Q1.csv

### Dataset Details:

Total Rows: 365,069
Total Columns: 12
### Column Information:

* Trip ID: A unique identifier for each trip record in the dataset.
* Start Time: The timestamp indicating the start time of the trip.
* End Time: The timestamp indicating the end time of the trip.
* Start Station ID: An ID representing the bike station where the trip started.
* Start Station Name: The name of the bike station where the trip started.
* End Station ID: An ID representing the bike station where the trip ended.
* End Station Name: The name of the bike station where the trip ended.
* User Type: Indicates whether the user is an annual membership holder ("subscriber") or a one-day pass holder ("customer").
* Gender: The gender of the user (if available).
* Birth Year: The birth year of the user (if available).

Note: Some users may not have provided gender or birth year information, resulting in missing values in the corresponding columns.

# Data Preparation

In this project, various libraries such as pandas, numpy, matplotlib.pyplot, datetime, and calendar will be utilized for data analysis. The dataset will undergo a cleansing process to ensure integrity and comprehensibility. Errors, wrong data types, and missing values will be addressed, and new columns will be added to facilitate analysis.

### Initial observations reveal:

* No duplicate rows in the dataset.
* Null values in the 'gender' (19711 entries) and 'birthyear' (18023 entries) columns.
* 'start_time' and 'end_time' columns are in object data type, and they will be converted to date format to extract useful date information.
* The 'tripduration' column has some data issues. The data type will be changed to integer, and values with separators (",") will be removed.
* Some trip durations are extremely long (up to 2952 hours), likely due to errors or unreturned bikes. These will be replaced with the mean duration of trips less than three hours.
* The 'gender' column will be filled with "Missing" for null values, and "Missing" values will be disregarded during analysis.
* The 'birthyear' column will be used to create the 'user_age' column, and extreme ages (above 80) will be replaced with the average age (41).
* Null values in the 'user_age' column will be filled with the average user age (41) to retain valuable data.

By performing these data preparation steps, the dataset will be ready for further analysis, enabling meaningful insights into city-wide biking trends during the first quarter of 2019.


# Data Insights

After cleaning and preparing the dataset, valuable insights have been derived from the analysis:
### Number of Divvy Trips, Most Used Bikes and Average Trip Duration

* Number of Divvy Trips: During the first quarter of 2019, a total of 365,069 Divvy trips were completed.

* Most Used Bikes: Among the fleet of Divvy bikes, the following bike IDs were the most frequently used for trips: 3457, 6407, 5983, 6074, and 3494. These bikes were utilized for a significant number of rides during the quarter.

<img width="393" alt="image" src="https://github.com/mohamedabdelnasser414/data-analysis-Bikeshare-Python/assets/56372404/e59225e1-0e3a-4080-92cb-1a14ca2a3a99">


* Average Trip Duration: The mean trip duration for all users during the first quarter of 2019 was approximately 12 minutes. However, when considering user types separately:

    * Subscription Riders: The average trip duration for subscription riders was around 11 minutes, which is lower than the overall mean trip duration.
    * Casual Riders: Casual riders, who hold one-day passes, had an average trip duration of approximately 31 minutes, which is significantly higher than the overall mean trip duration. This indicates that casual riders tend to use the bikes for longer durations compared to subscribers.
