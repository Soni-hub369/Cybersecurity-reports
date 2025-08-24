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

<img width="667" height="359" alt="Retrive after hour failed login attempts" src="https://github.com/user-attachments/assets/62bb1a66-7af7-4bba-8a95-148fcead6af9" />

---

## 2. Retrieve Login Attempts on Specific Dates  
A suspicious event occurred on **2022-05-09**, and I also needed to check the day before (**2022-05-08**).  

**Process:**  
- Selected all data from the `log_in_attempts` table.  
- Used a `WHERE` clause with `OR` to capture both dates.  
  - `login_date = '2022-05-09'`  
  - `login_date = '2022-05-08'`  

This provided all login activity from those two days for further investigation.  


<img width="664" height="311" alt="Retrive login attempts on specific dates" src="https://github.com/user-attachments/assets/36793694-645c-4dd4-bdf3-c1412c4aadac" />

---

## 3. Retrieve Login Attempts Outside of Mexico  
Some login attempts from outside Mexico appeared suspicious and needed review.  

**Process:**  
- Selected all data from the `log_in_attempts` table.  
- Used a `WHERE` clause with `NOT` and `LIKE`.  
  - `country NOT LIKE 'MEX%'` → excludes all attempts from Mexico (whether written as `MEX` or `MEXICO`).  

This query helped highlight logins from unusual locations.  

<img width="666" height="311" alt="retrive login attempts outside mexico" src="https://github.com/user-attachments/assets/fac931c1-7470-49f8-9df1-82f5222fd0a4" />

---

## 4. Retrieve Employees in Marketing (East Building)  
My team needed to update computers for Marketing employees located in the East building.  

**Process:**  
- Selected all data from the `employees` table.  
- Used a `WHERE` clause with `AND`.  
  - `department = 'Marketing'`  
  - `office LIKE 'East%'`  

This filtered the exact group of employees whose machines required updates. 
<img width="669" height="244" alt="retrive employees in marketing" src="https://github.com/user-attachments/assets/7cf3cc1a-af05-478e-aa99-d4a921546fa7" />


---

## 5. Retrieve Employees in Finance or Sales  
Computers for Finance and Sales employees needed different updates.  

**Process:**  
- Selected all data from the `employees` table.  
- Used a `WHERE` clause with `OR`.  
  - `department = 'Finance'`  
  - `department = 'Sales'`  

This gave me the full list of employees from both departments.  
<img width="662" height="265" alt="retrive employees in finance or sales" src="https://github.com/user-attachments/assets/36dd964a-4a78-4d2b-953f-ff9e0166eef2" />


---

## 6. Retrieve Employees Not in IT  
Finally, we needed to update computers for employees **outside the IT department**.  

**Process:**  
- Selected all data from the `employees` table.  
- Used a `WHERE` clause with `NOT`.  
  - `department != 'Information Technology'`  

This query provided all non-IT employees who required security updates. 
<img width="662" height="312" alt="Retrive all employees not in IT" src="https://github.com/user-attachments/assets/37965f94-f302-4725-a1df-bbc58c77a50c" />


---

## Summary  
I applied SQL filters to gather precise information about login activity and employee machines.  

- **Tables used:** `log_in_attempts` and `employees`  
- **Operators used:** `AND`, `OR`, `NOT`  
- **Pattern matching:** `LIKE` with `%` wildcard  

These queries helped investigate suspicious logins and identify which employees needed system updates, making the organization’s security stronger and more efficient.  

---
