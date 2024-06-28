# Using-SQL-Filters-For-Efficient-Security-Management
In this project, I employed SQL queries with filters to bolster system security. Tasks included investigating potential security issues, ensuring system safety, and efficiently updating employee computers based on identified security needs.

## Objective
The objective of this project is to enhance the overall security posture of the organization's systems through the systematic use of SQL queries with filters. Specifically, the project aims to identify security issues, ensure system safety, automate security tasks, optimize security management and enhance proactive security measures.

### Skills Learned
#### System Security Management: 
Experience in ensuring and enhancing system security within an organizational context.

#### Security Investigation: 
Skills in investigating and identifying potential security vulnerabilities and threats.

#### SQL Querying: 
Proficiency in writing SQL queries to filter and retrieve data for security analysis and management.

#### Patch Management: 
Ability to update and maintain employee computers with necessary security patches and configurations.

#### Risk Assessment: 
Understanding and assessing risks associated with system security and implementing appropriate measures.

#### Problem Solving:
Addressing security issues and finding effective solutions using SQL queries and filters.

#### Documentation: 
Documenting security findings, actions taken, and updates to maintain a clear record of security measures implemented.

## Tools used
#### SQL

## Workflow
#### Retrieve after-hours failed login attempts:
There was a potential security incident that occurred after business hours (after 18:00). All after-hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours:

![image](https://github.com/NanaYawAsareTakyi/Using-SQL-Filters-For-Efficient-Security-Management/assets/173400465/80eec650-fc89-4b98-a697-3ce5e93c2e26)

The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = 0, which filters for the failed login attempts. 

#### Retrieve login attempts on specific dates:
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates:

![image](https://github.com/NanaYawAsareTakyi/Using-SQL-Filters-For-Efficient-Security-Management/assets/173400465/11d2823f-42e0-4ae8-af0e-eb0d1f1026c0)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

#### Retrieve login attempts outside of Mexico:
After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico: 

![image](https://github.com/NanaYawAsareTakyi/Using-SQL-Filters-For-Efficient-Security-Management/assets/173400465/7f646b6f-efb9-47c7-aebb-6083e04e9052)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE. 

#### Retrieve employees in Marketing
My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building:

![image](https://github.com/NanaYawAsareTakyi/Using-SQL-Filters-For-Efficient-Security-Management/assets/173400465/b7ae769f-92f8-4cfb-8f55-6d1ecd833af0)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

#### Retrieve employees in Finance or Sales
The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments:

![image](https://github.com/NanaYawAsareTakyi/Using-SQL-Filters-For-Efficient-Security-Management/assets/173400465/46da5d9c-d32a-48d2-98af-c46917463bec)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

#### Retrieve all employees not in IT
My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department:

![image](https://github.com/NanaYawAsareTakyi/Using-SQL-Filters-For-Efficient-Security-Management/assets/173400465/5f80d510-bff7-404c-9cbd-37ff1315c65d)

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

## Summary
In this project, I utilized SQL queries with filters to extract precise information concerning login attempts and employee machines. This involved working with two distinct tables: "log_in_attempts" and "employees". To refine my queries effectively, I employed various SQL operators:

Logical Operators: I utilized the AND, OR, and NOT operators to combine conditions and filter for specific criteria in both the "log_in_attempts" and "employees" tables. This allowed me to extract data that met multiple criteria simultaneously or exclude data based on specific conditions.

Wildcard and Pattern Matching: Utilizing the LIKE operator along with the percentage sign (%) wildcard, I implemented pattern matching within my queries. This enabled me to search for and retrieve data that matched specified patterns or contained certain character sequences within fields, enhancing the flexibility and precision of my search queries.

By leveraging these SQL filtering techniques, I successfully retrieved targeted information on login attempts and employee machines, contributing to enhanced security monitoring and management within the organization. This experience equipped me with proficiency in SQL querying, data filtering, and pattern matching, essential skills for effective data analysis and security management roles.






