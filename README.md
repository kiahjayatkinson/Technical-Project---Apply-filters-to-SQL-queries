# Apply filters to SQL queries

## Project Description

In this project, I needed to obtain specific information about employees, their machines, and the departments they belong to from the database. My team needed data to investigate potential security issues and to update computers. I was responsible for filtering the required information from the database. In this project I used the MariaDB Server.

## Retrieve after hours failed login attempts

I investigated failed login attempts that were made after business hours. I retrieved this information from the login activity. I had to provide data that showed me unsuccessful attempts after 18:00. My commands in SQL are as follows: 

<img width="971" height="783" alt="image" src="https://github.com/user-attachments/assets/c5737be7-835a-4f43-a348-be4d648b63ec" />

SELECT *

FROM log_in_attempts

WHERE login_time > '18:00' AND success = FALSE;

I was able to clearly observe 19 login attempts were made after 18:00 from multiple countries.



## Retrieve login attempts on specific dates

Next my team wanted to investigate a suspicious event that occurred on 2022-05-09. I was tasked to retrieve all login attempts that occurred on this day and the day before (2022-05-08). I knew I would need to implement the OR operator for this task. My commands are as follows:

<img width="975" height="260" alt="image" src="https://github.com/user-attachments/assets/599e82b2-5b58-4ab0-a605-b510f6a5fc79" />
<img width="975" height="213" alt="image" src="https://github.com/user-attachments/assets/d7d0ac4b-e02e-4169-976c-e6ad5baeab80" />

SELECT * 

FROM log_in_attempts 

WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';

I cut out the bulk of the results here to save space. The query results showed me that these two days had a total of 75 login attempts.



## Retrieve login attempts outside of Mexico

Next, I was tasked to investigate logins that did not originate in Mexico. It was important to note that the country field includes entries with 'MEX' and 'MEXICO', so I knew that operators such as: ‘NOT’, ‘LIKE’ & ‘%’ would be useful in this situation. My commands are as follows:

<img width="975" height="238" alt="image" src="https://github.com/user-attachments/assets/f7430c36-d7ff-4866-bc32-5538f0044110" />
<img width="975" height="194" alt="image" src="https://github.com/user-attachments/assets/9ff778c2-026c-4efe-96f9-88805bd45ee7" />

SELECT * 

FROM log_in_attempts 

WHERE NOT country LIKE 'MEX%';

The results in this query provided me with 144 login attempts made outside of Mexico.

## Retrieve employees in Marketing

My team needed to update the employee machines. I was tasked with obtaining the information about employees in the 'Marketing' department who are located in all offices in the East building (such as 'East-170' or 'East-320'). First I ran a simple command to observe all employees:

<img width="975" height="231" alt="image" src="https://github.com/user-attachments/assets/efbac838-d5c5-4b95-92f3-a8ba36a80c3a" />
<img width="975" height="213" alt="image" src="https://github.com/user-attachments/assets/d1fdeced-6889-43fb-8e35-8701ac83c7d0" />

SELECT * 

FROM employees;

The results of this command gave me 200 rows of employees from different offices and departments. I needed to filter this query to find only the employees in the Marketing department who are located in the East building. My commands to retrieve this data are as follows:

<img width="969" height="464" alt="image" src="https://github.com/user-attachments/assets/d044b6f1-9d82-496d-8df4-f63add8fc7d8" />

SELECT * 

FROM employees 

WHERE department = 'Marketing' AND office LIKE 'East%';

This query returned results that showed 7 employees from the marketing department were located in the east building. The use of the AND operator was important here because it allowed me to return data with more than 1 condition (department & office location).

## Retrieve employees in Finance or Sales

My team needed to perform a different update to the computers of all employees in the Finance or the Sales department. I was tasked to locate information on these employees. I knew the use of the OR operator would be needed here to filter both conditions. My commands were as follows:

<img width="969" height="302" alt="image" src="https://github.com/user-attachments/assets/f1d15e4b-ea8c-410a-98b3-ff7e92cbddac" />
<img width="973" height="244" alt="image" src="https://github.com/user-attachments/assets/9607defa-f782-4907-9f91-fafee790d414" />

SELECT * 

FROM employees 

WHERE department = 'Finance' OR department = 'Sales';

The results of this query provided 71 employees from both the sales and finance departments.

## Retrieve all employees not in IT

Lastly, my team needed to make one more update. This update was already made to employee computers in the Information Technology department. My team needed information about employees who are not in that department. In this task I knew that the NOT operator would be important, so I could remove the IT department from my search. My commands are as follows:

<img width="973" height="298" alt="image" src="https://github.com/user-attachments/assets/0e86fe52-0e23-43b2-a3b5-c83eb2e40d4e" />
<img width="975" height="156" alt="image" src="https://github.com/user-attachments/assets/4d500637-0d6e-4ad7-a011-dc2487496f43" />

SELECT * 

FROM employees 

WHERE NOT department = 'Information Technology';

The results of this query provided me with 161 employees who were not from the IT department. I can then update the correct  machines excluding the IT department.

# Summary
I Successfully retrieved all required datasets using targeted SQL queries with appropriate operators (AND, OR, NOT, LIKE). The extracted data directly enabled security investigations into suspicious login patterns and facilitated precise machine updates for specific employee groups across departments and locations.



