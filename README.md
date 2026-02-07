<h1>Applying Filters to SQL Queries</h1>

<h2>Project Description</h2>
My organization is strengthening system security, and part of my role is to support security monitoring, investigate potential incidents, and assist with device updates when required. To accomplish these tasks, I used SQL queries with filtering conditions to analyze login activity and identify employee devices requiring updates. The following examples demonstrate how SQL filters were applied to security-related scenarios.
<br />

<h2>Identifying After-Hours Failed Login Attempts</h2>

A potential security incident occurred outside of business hours (after 18:00). All failed login attempts during this timeframe needed to be reviewed.

The query I created filters login records to return only failed attempts that occurred after 18:00. I selected data from the log_in_attempts table and applied a WHERE clause with an AND operator. The condition login_time > '18:00' isolated after-hours activity, while success = FALSE filtered for unsuccessful login attempts.

<p align="left">
<img src="https://i.imgur.com/jfuKO27.png" height="80%" width="80%" alt="Identifying After-Hours Failed Login Attempts"/>
<br />
  
<h2>Reviewing Login Activity on Specific Dates</h2>

A suspicious event was reported on 2022-05-09, requiring investigation of login activity from that date and the previous day.

To retrieve this data, I queried the log_in_attempts table and used a WHERE clause with an OR operator. The conditions login_date = '2022-05-09' and login_date = '2022-05-08' ensured that login attempts from both dates were included in the results.

<p align="left">
<img src="https://i.imgur.com/qb6iRLt.png" height="80%" width="80%" alt="Reviewing Login Activity on Specific Dates"/>
<br />

<h2>Identifying Login Attempts Outside of Mexico</h2>

During analysis, I identified potentially suspicious login attempts originating outside of Mexico that required further investigation.

I filtered the log_in_attempts table using a WHERE clause with NOT and LIKE. Because the dataset represents Mexico as both MEX and MEXICO, I used the pattern MEX%. The percent sign (%) wildcard allowed the query to match any additional characters following the prefix.
<p align="left">
<img src="https://i.imgur.com/TkH2soA.png" height="80%" width="80%" alt="Identifying Login Attempts Outside of Mexico"/>
<br />

<h2>Retrieving Employees in the Marketing Department</h2>

My team needed to deploy system updates to employees in the Marketing department located in the East building.

I queried the employees table and used a WHERE clause with an AND operator to filter for employees in the Marketing department and assigned to offices in the East building. The LIKE 'East%' condition was used to account for varying office numbers associated with that location.

<p align="left">
<img src="https://i.imgur.com/CVv98BX.png" height="80%" width="80%" alt="Retrieving Employees in the Marketing Department"/>
<br />

<h2>Retrieving Employees in Finance or Sales</h2>

Employees in the Finance and Sales departments required a separate security update.

To identify these users, I filtered the employees table using a WHERE clause with the OR operator. This returned all employees whose department was either Finance or Sales.

<p align="left">
<img src="https://i.imgur.com/rkgy8O1.png" height="80%" width="80%" alt="Retrieving Employees in Finance or Sales"/>
<br />
  
<h2>Identifying Employees Not in IT</h2>

An additional update needed to be applied to all employees outside of the Information Technology department.

I created a query using the employees table and applied a WHERE clause with NOT to exclude employees in the IT department, returning only those who required the update.

<p align="left">
<img src="https://i.imgur.com/pPjil1z.png" height="80%" width="80%" alt="Identifying Employees Not in IT"/>
<br />

<h2>Summary</h2>

In this task, I applied SQL filters to retrieve targeted data related to login activity and employee devices. I queried two tables—log_in_attempts and employees—and used logical operators such as AND, OR, and NOT to refine results. I also used the LIKE operator and wildcard characters to match patterns within the data. These techniques supported security investigations and system maintenance efforts.
