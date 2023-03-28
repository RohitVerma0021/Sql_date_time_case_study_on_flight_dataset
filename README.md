# SQL Date Time Case Study on Flights Dataset in MySQL
This project is a case study on a flights dataset using MySQL to explore and analyze the data using date and time functions.
## Dataset
The flights dataset used in this project contains data on flights with around 10030, including information such as flight date, origin and destination airports, departure and arrival times, and various other flight details. The dataset can be found at [Flight data](https://github.com/RohitVerma0021/Sql_date_time_case_study_on_flight_dataset/blob/main/cleand_laptop_data.csv)
## SQL Queries
Several SQL queries were used to analyze the flights dataset in MySQL, including:
#### Query 1: ```
              AVG(CASE WHEN HOUR(departure) BETWEEN 0 AND 5 THEN Price ELSE NULL END) AS '12AM-6AM',
              AVG(CASE WHEN HOUR(departure) BETWEEN 6 AND 11 THEN Price ELSE NULL END) AS '6AM-12PM',
              AVG(CASE WHEN HOUR(departure) BETWEEN 12 AND 17 THEN Price ELSE NULL END) AS '12PM-6PM',
              AVG(CASE WHEN HOUR(departure) BETWEEN 18 AND 23 THEN Price ELSE NULL END) AS '6PM-12PM'
              FROM flights
              WHERE Source = 'Banglore' AND Destination = 'Delhi'
              GROUP BY DAYNAME(departure)
              ORDER BY DAYOFWEEK(departure) ```
#### Query Explanation: 
- This is an SQL query that calculates the **`average`** price of flights departing from **'Banglore'** and arriving at **'Delhi'**, **`grouped`** by the day of the week and time of day. It uses **`CASE`** statements to check the hour component of the **`departure`** time and calculate the **`average`** price of flights that fall into each time range. The query then groups the data by day of the week and sorts it in **`ascending order`**.
#### Query 2: ```
                SELECT DAYNAME(departure),
                SUM(CASE WHEN HOUR(departure) BETWEEN 0 AND 5 THEN 1 ELSE 0 END) AS '12AM-6AM',
                SUM(CASE WHEN HOUR(departure) BETWEEN 6 AND 11 THEN 1 ELSE 0 END) AS '6AM-12PM',
                SUM(CASE WHEN HOUR(departure) BETWEEN 12 AND 17 THEN 1 ELSE 0 END) AS '12PM-6PM',
                SUM(CASE WHEN HOUR(departure) BETWEEN 18 AND 23 THEN 1 ELSE 0 END) AS '6PM-12AM',
                COUNT(*)
                FROM flights WHERE Source ='Banglore' AND Destination='Delhi'
                GROUP BY DAYNAME(departure)
                ORDER BY DAYOFWEEK(departure);```
#### Query Explanation: 
- This is an SQL query that counts the number of flights departing from 'Banglore' and arriving at 'Delhi', grouped by the day of the week and time of day. It uses **`CASE`** statements to check the hour component of the **`departure`** time and count the number of flights that fall into each time range. The query also includes a **`COUNT(*)`** statement to count the total number of flights for each day of the week. The query then groups the data by day of the week and sorts it in ascending order.
## Date and Time Functions Used
To analyze the flights data, several date and time functions were used in MySQL, including:

- [MONTH()](https://dev.mysql.com/doc/heatwave/en/mys-hw-date-functions.html): to extract the month from a date
- [YEAR()](https://dev.mysql.com/doc/heatwave/en/mys-hw-date-functions.html): to extract the year from a date
- [DATE_FORMAT()](https://dev.mysql.com/doc/heatwave/en/mys-hw-date-functions.html): to format a date or time value
- [TIMESTAMPDIFF()](https://dev.mysql.com/doc/heatwave/en/mys-hw-date-functions.html): to calculate the difference between two timestamps
- [DATE_ADD()](https://dev.mysql.com/doc/heatwave/en/mys-hw-date-functions.html): to add or subtract a specific amount of time from a date or time value

## Results
The results of the SQL queries and analysis can be found in [name of results file or folder], including [description of what the results show and any insights gained from the analysis].
## Requirements
To run the SQL queries and analysis on the flights dataset in MySQL, the following software and tools are required:

- MySQL server
- MySQL client, such as MySQL Workbench or the MySQL command-line client
## Usage
To use this project, follow these steps:
1. Download the flights dataset from [Flight data](https://github.com/RohitVerma0021/Sql_date_time_case_study_on_flight_dataset/blob/main/cleand_laptop_data.csv) and save it to your computer.
2. Open MySQL Workbench or the MySQL command-line client.
3. Create a new database and import the flights dataset into a new table.
4. Copy and paste the SQL queries from [name of SQL file or folder] into MySQL Workbench or the MySQL command-line client.
5. Connect to the flights dataset in MySQL.
6. Run the SQL queries to analyze the flights data and view the results in [name of results file or folder].





