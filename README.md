# Technical Project - Apply filters to SQL queries

## Project Description

In this project, I needed to obtain specific information about employees, their machines, and the departments they belong to from the database. My team needed data to investigate potential security issues and to update computers. I was responsible for filtering the required information from the database. 

## Retrieve after hours failed login attempts

I investigated failed login attempts that were made after business hours. I retrieved this information from the login activity. I had to provide data that showed me unsuccessful attempts after 18:00. My commands in SQL are as follows: 

<img width="971" height="783" alt="image" src="https://github.com/user-attachments/assets/c5737be7-835a-4f43-a348-be4d648b63ec" />

SELECT *

FROM log_in_attempts

WHERE login_time > '18:00' AND success = FALSE;

I was able to clearly observe 19 login attempts were made after 18:00 from multiple countries.



## Retrieve login attempts on specific dates

Next my team wanted to investigate a suspicious event that occurred on 2022-05-09. I was tasked to retrieve all login attempts that occurred on this day and the day before (2022-05-08). I knew I would need to implement the OR operator for this task. My commands are as follows:

<img width="975" height="260" alt="image" src="https://github.com/user-attachments/assets/e03b6286-b154-427f-a76b-a5b1156084d9" />
