# Case Study: Attendance Management System in SQL

This case study involves managing an attendance system for an organization. The system tracks employees, their attendance, departments, holidays, leave requests, and work schedules. The task is to create the necessary tables, insert records, and perform various SQL queries to manage and analyze the data.

## Database Schema:

### Employees
- `EmployeeID` (INT, Primary Key)
- `FirstName` (VARCHAR)
- `LastName` (VARCHAR)
- `Email` (VARCHAR)
- `Phone` (VARCHAR)
- `Department` (VARCHAR)
- `HireDate` (DATE)

### Departments
- `DepartmentID` (INT, Primary Key)
- `DepartmentName` (VARCHAR)
- `Location` (VARCHAR)

### Attendance
- `AttendanceID` (INT, Primary Key)
- `EmployeeID` (INT, Foreign Key referencing Employees.EmployeeID)
- `Date` (DATE)
- `CheckInTime` (DATETIME)
- `CheckOutTime` (DATETIME)
- `Status` (VARCHAR) — e.g., 'Present', 'Absent', 'Late'

### Holidays
- `HolidayID` (INT, Primary Key)
- `HolidayDate` (DATE)
- `HolidayName` (VARCHAR)

### LeaveRequests
- `LeaveRequestID` (INT, Primary Key)
- `EmployeeID` (INT, Foreign Key referencing Employees.EmployeeID)
- `StartDate` (DATE)
- `EndDate` (DATE)
- `LeaveType` (VARCHAR) — e.g., 'Sick', 'Vacation'
- `Status` (VARCHAR) — e.g., 'Approved', 'Pending', 'Rejected'

### WorkSchedules
- `ScheduleID` (INT, Primary Key)
- `EmployeeID` (INT, Foreign Key referencing Employees.EmployeeID)
- `StartTime` (TIME)
- `EndTime` (TIME)
- `ScheduleDate` (DATE)

## SQL Queries:

### 1. Create Table:
Write an SQL statement to create all tables with the specified columns.

### 2. Insert Records:
Insert at least 10 records in all the tables.

### 3. Select Records:
Write a query to select all attendance records from the Attendance table where the Status is 'Late'.

### 4. Where Clause (AND/OR):
Write a query to select all employees from the Employees table who work in the 'HR' department and were hired after January 1, 2020.

### 5. LIKE Operator:
Write a query to select all departments where the DepartmentName contains 'Sales'.

### 6. CASE Statement:
Write a query to select `CheckInTime`, `CheckOutTime`, and a new column `AttendanceDuration` from the Attendance table. Calculate `AttendanceDuration` as the difference between `CheckOutTime` and `CheckInTime`.

### 7. Subquery:
Write a query to find all employees who have at least one 'Approved' leave request. Use a subquery in the `WHERE` clause to find these `EmployeeIDs`.

### 8. Group By:
Write a query to get the total number of days each employee was present in the current month. Group the results by `EmployeeID`.

### 9. Having Clause:
Write a query to get the total number of leave requests for each employee, but only include employees with more than 3 leave requests. Use the `HAVING` clause.

### 10. Limit:
Write a query to select the top 5 employees with the most number of 'Absent' statuses in the past year.

### 11. Inner Join:
Write a query to join `Employees` with `Departments` to get a list of all employees with their department names.

### 12. Outer Join:
Write a query to get a list of all employees and any associated `LeaveRequests`. Include employees who might not have any leave requests.

### 13. Join with Aggregation:
Write a query to get the average number of hours worked per day for each employee. Use an `INNER JOIN` between `WorkSchedules` and `Attendance`, and group by `EmployeeID`.

### 14. Subquery with Join:
Write a query to find all employees who have worked on days that are holidays. Use a subquery to filter dates that are in the `Holidays` table.

### 15. Advanced Join:
Write a query to list `FirstName`, `LastName`, `DepartmentName`, and `HolidayName` for all employees who have their `CheckInTime` on a holiday. Use `INNER JOIN` and `LEFT JOIN` as necessary to get all required details.
