Repository

This repo contains my Capstone project for the Google data analytic program I just completed.It demonstrate the data analysis skills I gained and earned fro the course.
In this project, I will be utilizing the skills earned from the course on data cleaning, processing and analysis to a solve a business senerio on bike sharing company.
The objective of the bike sharing company is to convert casual riders to annual members and develope a marketing strategy that will enable the company to acheive this purpose.
R programming language and SQL has been used as tool to ensure data cleaning and analysis.


Executive Summary

The bike-share program by the Cyclistic company is a unique system which allows options to different bikes. The fact remains that a bike share system is mostly used for shorter distances, exercises or for leisure however, its revenue generation potential enables the system to be a viable project which attracts funding from investors.

Introduction

A bike-share system is a practise which allows prospective riders interested in making use of a bike to have access to a bike for a specified period of time. This can also be described as a program that enables intended riders to check-out bikes whenever they are interested through the use of an App specifically for a bike-share system. The system automates the bike access through the App which unlocks the bike from the rack and takes records of the ride in the system from the time the rider starts the ride till when the bike is returned to the rack which signifies the end of the ride.
To achieve a successful system, the bike-share program must embrace flexibility in it process management and pricing system. This will enable intended riders to have options to the type of prices available on the bike-share App. This can be a single ride pass, a return to same location pass, half-dsy ride pass, full-day ride pass etc. The bike-share program can also allow membership subscriptions such as annual, monthly or quarterly. The essence of this subscription option is to build a bike-share community to ensure the goals and objectives of the system is actualized.

The benefits of a bike-share program are

1.	It embraces a sociable business model which encourages networking among different individuals.
2.	It supports a healthy environment by reducing carbon emission.
3.	It discourages noise pollution 
4.	It can also be cost efficient to the rider.
5.	
PROBLEM STATEMENT.

This project shall examine the following problems
1.	The disparity in the membership structure of the bike-share program.
2.	Low market share and penetration
3.	Why will casual riders be interested in becoming annual members.
The fact remains that every business structure has challenges which keeps the management of the business to profound solutions so has to ensure a speedy success. There is a need to examine the root cause of this problem. 

PROJECT STAKEHOLDERS

As a junior data analyst working with the marketing analyst team at cyclistic bike-share company in Chicago, the task is to analyse data to formulate a marketing strategy that will pave a successful business operation for the bike-share company. 
The stakeholders for this project include Lily Moreno who is the director of marketing, the director of finance, the director of operations, the cyclitic marketing analytics team who are responsible for collecting, analysing and reporting data to guide  Cyclistic marketing strategy, the executive team of the company as well as prospective bike riders.

ROOT CAUSE ANALYSIS

Following the request of the bike-share company, the directors want to increase annual membership. The following questions set 
•	Why does the company want to improve annual membership? This might certainly be because they have in their database more of casual riders whose revenue are not sustainable.
•	Why are they more casual riders? This may simply be because the fee charge on riders are affordable and riders only ride on a short distance and they are on-off.
•	Why is the revenue from casual riders not sustainable? This may be because it barely used to maintain the bikes hence, no profit is realized to ensure continuity of the business.
•	Why are there no profit realized? This may be because most casual riders affors single ride.
•	Why do they afford single rides? This is because they are not constant.
Following the root cause specified above, it is factual that the bike-share company need to device a strategy that will allow casual riders to subscribe to the annual membership program so as to ensure increase in revenue that will be sustainable to the business alongside realizing more profit that will exceed the cost of maintenance.

OBJECTIVE OF THE STUDY

The following are the objectives of this project

1.	To formulate a marketing strategy for the bike-share program.
2.	To bridge the gap between casual and annual membership.

PREPARE PHASE
DATA CLEANING AND PROCESSING

This project shall be using Cyclic bike share data for the period January to March 2023 provided by the Google Data Analytics Course. The dataset is a comma-separated value format (.csv).
The raw dataset can be viewed at the following link https://divvy-tripdata.s3.amazonaws.com/index.html
The dataset contains entries for each trip/ride taken with Cyclistic bicycles.
This pre-cleaned dataset contains a total of 5734381 entries across 12 tables, and includes the following fields:
•	ride_id: unique identifier for each entry
•	rideable_type: type of bicycle used
•	started_at: date & time where ride started
•	ended_at: date & time where ride ended
•	start_station_name: name of bicycle station at start of the ride
•	start_station_id: unique identifier for bicycle station at start of the ride
•	end_station_name: name of bicycle station at end of the ride
•	end_station_id: unique identifier for bicycle station at end of the ride
•	start_lat: latitude of station at start of the ride
•	start_lng: longitude of station at start of the ride
•	end_lat: latitude of station at end of the ride
•	end_lng: longitude of station at end of the ride
•	member_casual: indication of whether customer is a Cyclistic annual member or casual rider

Furthermore, in line with the privacy ethics, the personal information of riders were not included in this study. This implies that informations such as purchase history, credit card details, demographic locations cannot be explored within the scope of this project.

The dataset contains entries for each trip/ride taken with Cyclistic bicycles within the the period January to March 2023. The data cleaning process is aim at ensuring all relevant information is used in the analysis. The cleaned relevant variables 
Data analysis

Data analysis is performed using R, within the RStudio interface. Appropriate R extensions are utilized, namely the tidyverse package for data analysis.

We will be looking at analysis for the following, for both annual members and casual riders, comparing the two groups where appropriate:

1.	Total rides taken by the first quarter in 2023
2.	The rideable bikes used 
3.	duration of trips.
4.	 Start and end lat and lng
The Big query SQL programming was also used to filter and analyse the data. This was achieved by copying the cleaned dataset from R studio and then uploading it into SQL to create a table bikeshare_ride.

SELECT 
ride_id,
rideable_type,
start_lat_lng,
end_lat_lng,
start_time,
end_time,
duration,
member_casual

 FROM `commanding-port-426503-j6.employee_data.bikeshare_ride` 
 LIMIT 1000


SELECT 
ride_id,
rideable_type,
start_lat_lng,
end_lat_lng,
start_time,
end_time,
duration,
member_casual
 FROM `commanding-port-426503-j6.employee_data.bikeshare_ride` 
 WHERE
 rideable_type = 'electric_bike'
 AND member_casual = 'member'

 LIMIT 1000

SELECT 
ride_id,
rideable_type,
start_lat_lng,
end_lat_lng,
start_time,
end_time,
duration,
member_casual
 FROM `commanding-port-426503-j6.employee_data.bikeshare_ride` 
 WHERE
member_casual = 'member'
AND rideable_type = 'classic_bike'
LIMIT 1000

From the above SQL language, 107 annual members actual took a bike ride between January to March 2023 which is further analysed into the following rideable bike as; 52 electric bikes were rode, 55 for classic bikes and none took docked bikes in the period considered.

SELECT 
ride_id,
rideable_type,
start_lat_lng,
end_lat_lng,
start_time,
end_time,
duration,
member_casual

 FROM `commanding-port-426503-j6.employee_data.bikeshare_ride` 
 
 WHERE
member_casual = 'casual'
AND rideable_type = 'classic_bike'
LIMIT 1000
SELECT 
ride_id,
rideable_type,
start_lat_lng,
end_lat_lng,
start_time,
end_time,
duration,
member_casual

 FROM `commanding-port-426503-j6.employee_data.bikeshare_ride` 
 WHERE
member_casual = 'casual'
AND rideable_type = 'electric_bike'
LIMIT 1000

From the above SQL language, 37 casual actually took a bike ride between January to March 2023 which is further analysed into the following rideable bike as; 23 electric bikes were rode, 12 for classic bikes and 2 took docked bikes in the period considered.
It can be understood from the above that more bike riders subscribe to the annual membership within the period under review however, the flexibility in the bike-share system allows high maintenance cost on the bikes due to long distances observed from casual riders.

SELECT 
rideable_type,
member_casual,
duration,
FROM `commanding-port-426503-j6.employee_data.bikeshare_ride` 
WHERE
member_casual = 'member'
LIMIT 1000

Setting up the environment

RStudio is first loaded up with the tidyverse packages, followed by the import of our processed bikeshare_data.csv form my computer.

install.packages("tidyverse")
install.packages("skimr")
install.packages("janitor")

> library(tidyverse)
── Attaching core tidyverse packages ─────────────────────────────────────────────────── tidyverse 2.0.0 ──
✔ dplyr     1.1.2     ✔ readr     2.1.4
✔ forcats   1.0.0     ✔ stringr   1.5.0
✔ ggplot2   3.4.2     ✔ tibble    3.2.1
✔ lubridate 1.9.2     ✔ tidyr     1.3.0
✔ purrr     1.0.2     
── Conflicts ───────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
> 
ℹ Use the conflicted package to force all conflicts to become errors

> library(skimr)
> library(janitor)

Attaching package: ‘janitor’
colnames(bikeshare)
 [1] "ride_id"            "rideable_type"      "started_at"         "start_time"        
 [5] "ended_at"           "end_time"           "start_station_name" "start_station_id"  
 [9] "end_station_name"   "end_station_id"     "start_lat"          "start_lng"         
[13] "end_lat"            "end_lng"            "member_casual"     

skim_without_charts(bikeshare)
── Data Summary ────────────────────────
                           Values   
Name                       bikeshare
Number of rows             639423   
Number of columns          15       
_______________________             
Column type frequency:              
  character                9        
  difftime                 2        
  numeric                  4        
________________________            
Group variables            None     

── Variable type: character ───────────────────────────────────────────────────────────────────────────────
  skim_variable      n_missing complete_rate min max empty n_unique whitespace
1 ride_id                    0         1       8  16     0   639377          0
2 rideable_type              0         1      11  13     0        3          0
3 started_at                 0         1      16  16     0       90          0
4 ended_at                   0         1      16  16     0       93          0
5 start_station_name     88104         0.862  10  50     0     1102          0
6 start_station_id       88236         0.862   2  12     0     1065          0
7 end_station_name       93016         0.855  10  51     0     1120          0
8 end_station_id         93157         0.854   2  35     0     1081          0
9 member_casual              0         1       6   6     0        2          0

── Variable type: difftime ────────────────────────────────────────────────────────────────────────────────
  skim_variable n_missing complete_rate min    max        median n_unique
1 start_time            0             1 0 secs 86399 secs 14:58     72889
2 end_time              0             1 0 secs 86399 secs 15:08     72856

── Variable type: numeric ─────────────────────────────────────────────────────────────────────────────────
  skim_variable n_missing complete_rate  mean     sd    p0   p25   p50   p75  p100
1 start_lat             0         1      41.9 0.0477  41.6  41.9  41.9  41.9  42.1
2 start_lng             0         1     -87.6 0.0282 -87.8 -87.7 -87.6 -87.6 -87.5
3 end_lat             426         0.999  41.9 0.0478  41.6  41.9  41.9  41.9  42.1
4 end_lng             426         0.999 -87.6 0.0282 -87.9 -87.7 -87.6 -87.6 -87.5

trimmed_df <- bikeshare %>% 
+     select(rideable_type, start_station_name, start_time, end_station_name, end_time, start_lat, start_lng, end_lat, end_lng, member_casual)

example_df <- bikeshare %>%
+           select(start_lat, start_lng) %>% 
+           unite(start_lat_lng, c("start_lat", "start_lng"), sep = " ")

example_df <- bikeshare %>% mutate(start_lat_lng = start_lat + start_lng)
example_df <- bikeshare %>% mutate(end_lat_lng = end_lat + end_lng)
example_df <- bikeshare %>% mutate(duration = end_time - start_time
