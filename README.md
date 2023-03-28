# SQL Date Time Case Study on Flights Dataset in MySQL
This project is a case study on a flights dataset using MySQL to explore and analyze the data using date and time functions.
## Dataset
The flights dataset used in this project contains data on flights with around 10030, including information such as flight date, origin and destination airports, departure and arrival times, and various other flight details. The dataset can be found at [Flight data](https://github.com/RohitVerma0021/Sql_date_time_case_study_on_flight_dataset/blob/main/cleand_laptop_data.csv)
## SQL Queries
Several SQL queries were used to analyze the flights dataset in MySQL, including:
- Query 1: ``` AVG(CASE WHEN HOUR(departure) BETWEEN 0 AND 5 THEN Price ELSE NULL END) AS '12AM-6AM',
              AVG(CASE WHEN HOUR(departure) BETWEEN 6 AND 11 THEN Price ELSE NULL END) AS '6AM-12PM',
              AVG(CASE WHEN HOUR(departure) BETWEEN 12 AND 17 THEN Price ELSE NULL END) AS '12PM-6PM',
              AVG(CASE WHEN HOUR(departure) BETWEEN 18 AND 23 THEN Price ELSE NULL END) AS '6PM-12PM'
              FROM flights
              WHERE Source = 'Banglore' AND Destination = 'Delhi'
              GROUP BY DAYNAME(departure)
              ORDER BY DAYOFWEEK(departure) ```
- Query Explanation: 
--
