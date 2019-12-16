# Citibike Analysis

## Overview:
Cycling has become an increasingly significant part of the commuting routine for many New Yorkers. And a large portion of the cyclists in the city rely on Citibike to rent bicycles. According to the citibike business model citbike customers fall into two groups - full year subscribers or customers either using a day pay or a single ride pass. And that classification brings me to my question. 

## Question:
Can I use information about citibike riders such as age, gender, and start and stop station to determine whether they are renters or customers?

## Data:
The data used in my study originates from [Citibike system data](https://www.citibikenyc.com/system-data) and contained about 350,000 rows of data. 

Data used after dropping extraneous columns includes: trip duration (seconds), start time and date, stop time and date, start station name, end station name, station lat/long, user type (customer = 24-hour pass or 3-day pass user; subscriber = annual member), gender, birth year. 

## Feature Engineering:
By parsing the start time and date columns I was able to add columns containing whether a rider started their ride in the morning (before 12), afternoon(between 12-6), or night(after 6). Additionally using the **Google Distance Matrix API** I calculated the distance between all riders start and stop stations to determine how far they were travelling in meters. The Google Distance Matrix API takes coordinates or location names and calculates the distance between them by the way of the road. 

When using the good distance matrix API I included an advaced critiria to spicify the mode of transport as by bicycle to give the highest level of accuracy because there are often times where cyclists travel on paths cars cannot use. 

## Exploratory Data Analysis:
Taking a first look at my data 

Subscribers vs customers             |  Rider age distribution    
:-------------------------:|:-------------------------:
![alt_text](graphs/customer_vs_subscribers.png)  | ![alt_text](graphs/age_distribution.png)


Biking day distribution              |  Biking time distribution    
:-------------------------:|:-------------------------:
![alt_text](graphs/biking_days.png)  | ![alt_text](graphs/biking_time.png)

![alt_text](graphs/rental_stations.png)

![alt_text](graphs/docking_stations.png)
