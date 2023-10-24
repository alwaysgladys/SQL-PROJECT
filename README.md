# Unveiling Business Insights: A Deep Dive into 10 Critical Questions with Advanced SQL Techniques
## Introduction:
In the dynamic landscape of modern business operations, data-driven decision-making stands as a cornerstone for success. SQL, the ubiquitous language for managing and analyzing relational databases, empowers businesses to extract invaluable insights from their data reservoirs.
This project embarks on a journey through ten critical business questions, each unraveling a unique facet of organizational performance.
Leveraging advanced SQL techniques including aggregate functions, group by, having, row number, join, and subquery, we delve into the heart of data-driven decision-making.
The utilization of aggregate functions allows us to distill vast datasets into meaningful summaries, providing a macroscopic view of business performance. 
Coupled with the power of GROUP BY, we gain the ability to dissect data across various dimensions, enabling a nuanced understanding of key metrics. HAVING, as a filtering mechanism, empowers us to isolate specific subsets of data, ensuring that only the most pertinent information informs our decision-making process.

With each critical business question, we demonstrate the practical application of these advanced SQL techniques, unveiling the transformative potential they hold for organizational strategy.

## Problem Satement:

You are to come up with 10 critical business questions and provide answers to them. Use the dataset provided to ensure solutions have needs for the following command:
* Aggregate functions
*  Group by
*   Having
*  Row_Number()
*   Join
*  Subquery

## Questions:
1. Using the Department table, write a query to find the unique department with Designation. Return Dept ID and Designation.
2. Calculate the average yearly increment of the employees. Return the average yearly increment.
3. Using the Employee table, Identify the employhees from the city of Delhi with their Dept ID, email, and Phone numberf.
4. Using the salary table and the employee table, Identify the top 10 employees with the highest salary and their cities.
5. Calculate the average salary of the employees from the city of Mumbai.
6. Calculate the total number of pincodes in Delhi with the names of the employees.
7. Calculate the total number of employees from Pune city.
8. Using the Salary table, Identify the employees whose yearfly increment is less than the average salary increment.
9. Using the Department table and the employee table, run a query that returns the name, email, education and designation of the employees.
10. Using the Salary table, identify the employees with the highest salary ranking from the highest to the lowest.

## Solutions:


![DEPARTMENT ID AND DESIGNATION](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/f6db36b7-828d-4347-82b9-a5964acc3724)


The screenshot above shows the Dept ID and Designation of the employees. The syntax used is as follows;

*SELECT DISTINCT Dept ID, Designation FROM Department;*


![AVERAGE YEARLY INCREMENT](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/d46d126e-f25c-4e6b-9fee-7a56a77086a0)


The image above displays the average yearly increment of the employees and the synatx used is as follows;
*SELECT AVG(`Yearly increment`) FROM table_name;*


![Employees from DELHI](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/26aa8791-665d-4773-9537-f60bf6be3056)


The screenshot above shows the employees who live in the city of Delhi with their Dept ID, email, and Phone number. The syntax used is as follows;

*SELECT Name, email, phone, DeptID FROM Table_name WHERE City = “Delhi” ORDER BY City;*


![TOP 10 EMPLOYEES AND THEIR CITIES](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/4b9ea912-a1c1-4943-881d-81e77bdba9d4)


In this screenshot, we joined two tables which is the Employee table and the Salary table to be able to achieve our desired results which is the top 10 employees with the highest salary and their cities. The synatx used is as follows;
*SELECT Name, Salary, city FROM employee JOIN Salary ON employee.empID = salary.empID ORDER BY salary DESC LIMIT 10;*


![AVERAGE SALARY FOR THE CITY OF MUMBAI](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/cd57537d-f176-40d2-97dd-0247cc1274d1)


Here, we also joined the employee table and the salary table to achieve this particular result which is the average salary of the employees from the city of Mumbai. the syntax used is as follows:
*SELECT AVG(salary) FROM employee JOIN salary ON employee.empID = salary.empID WHERE City = "Mumbai";*


![NUMBER OF PINCODE](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/b3a15542-4d97-4515-b048-3150c15680f3)


The above image displays the total number of pincodes in the city of Delhi with the names of the employees and the syntax used is:
*SELECT Name, COUNT(pincode) AS Number of pincode FROM Table_name WHERE city = "Delhi" GROUP BY email HAVING `Number of pincode` = 1;*


![TOTAL NUMBER OF EMPLOYEES FROM PUNE CITY](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/a6259090-366b-4a7a-aeb0-f154bd56e78c)


The above screenshot shows the total count of the employees who are from the city of Pune and the command used to achieve it reads as follows;
*SELECT COUNT(Employee Name) WHERE City = "Pune";*



![SUBQUERY FOR YEARLY INCREMENT](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/c0d22113-64bd-449a-88af-72aa5438a73b)


The screenshot above illustrates the IDs of employees whose yearly salary increment is less than the average salary increment in the salary table and the syntax used is as follows;

*SELECT EmpID FROM salary WHERE `Yearly Increment` < (SELECT AVG(YearlyIncrement) FROM salary);*


![NAME, EMAIL,EDUCATION AND DESIGNATION](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/5b99cbc6-10bf-4222-b22d-031ce7d428db)


The screenshot above displays name, email, education and designationfrom the "Employee" and "Department" tables, joined based on the "EmpID" column. The syntax used is as follows;

*SELECT name, email, education, designation FROM Employee JOIN Department ON employee.DeptID = department.DeptID;*


![ROW NUMBER FOR SALARY RANKING](https://github.com/alwaysgladys/SQL-PROJECT/assets/144185133/c13ec94e-4a06-4320-879a-545d3fa28aed)


This screenshot displays the employees salary ranking as number from the highest salary to the lowest salary on the Salary table. The command used reads as follows;
*SELECT emp.ID, Base ROW_NUMBER() OVER (ORDER BY Base DESC) AS Number FROM Salary;*

## Conclusion:
 This project has delved into the realm of critical business questions through the powerful lens of SQL, employing a diverse array of techniques including aggregate functions, group by, having, row number, join, and subquery. 
 Through this exploration, we've not only uncovered insights but also developed a robust framework for extracting valuable information from complex datasets.
