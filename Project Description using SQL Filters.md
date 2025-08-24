# Project Description: Using SQL Filters for Security Tasks

My organization is working to strengthen its system security. My role is to ensure the system stays safe, investigate potential threats, and keep employee computers updated when necessary.  

Below are examples of how I used SQL filters to perform different security-related tasks.

============================================================

## 1. Retrieve Failed Login Attempts After Hours  
A possible security incident happened after business hours (after 18:00). To investigate, I needed to find all failed login attempts that occurred during that time.  

**Process:**  
- Selected all data from the `log_in_attempts` table.  
- Used a `WHERE` clause with `AND` to filter the results.  
  - `login_time > '18:00'` → only shows attempts after 18:00.  
  - `success = FALSE` → only shows failed login attempts.  

This query helped identify suspicious login activity after hours.  

---

## 2. Retrieve Login Attempts on Specific Dates  
A suspicious event occurred on **2022-05-09**, and I also needed to check the day before (**2022-05-08**).  

**Process:**  
- Selected all data from the `log_in_attempts` table.  
- Used a `WHERE` clause with `OR` to capture both dates.  
  - `login_date = '2022-05-09'`  
  - `login_date = '2022-05-08'`  

This provided all login activity from those two days for further investigation.  

---

## 3. Retrieve Login Attempts Outside of Mexico  
Some login attempts from outside Mexico appeared suspicious and needed review.  

**Process:**  
- Selected all data from the `log_in_attempts` table.  
- Used a `WHERE` clause with `NOT` and `LIKE`.  
  - `country NOT LIKE 'MEX%'` → excludes all attempts from Mexico (whether written as `MEX` or `MEXICO`).  

This query helped highlight logins from unusual locations.  

---

## 4. Retrieve Employees in Marketing (East Building)  
My team needed to update computers for Marketing employees located in the East building.  

**Process:**  
- Selected all data from the `employees` table.  
- Used a `WHERE` clause with `AND`.  
  - `department = 'Marketing'`  
  - `office LIKE 'East%'`  

This filtered the exact group of employees whose machines required updates.  

---

## 5. Retrieve Employees in Finance or Sales  
Computers for Finance and Sales employees needed different updates.  

**Process:**  
- Selected all data from the `employees` table.  
- Used a `WHERE` clause with `OR`.  
  - `department = 'Finance'`  
  - `department = 'Sales'`  

This gave me the full list of employees from both departments.  

---

## 6. Retrieve Employees Not in IT  
Finally, we needed to update computers for employees **outside the IT department**.  

**Process:**  
- Selected all data from the `employees` table.  
- Used a `WHERE` clause with `NOT`.  
  - `department != 'Information Technology'`  

This query provided all non-IT employees who required security updates.  

---

## Summary  
I applied SQL filters to gather precise information about login activity and employee machines.  

- **Tables used:** `log_in_attempts` and `employees`  
- **Operators used:** `AND`, `OR`, `NOT`  
- **Pattern matching:** `LIKE` with `%` wildcard  

These queries helped investigate suspicious logins and identify which employees needed system updates, making the organization’s security stronger and more efficient.  

---
