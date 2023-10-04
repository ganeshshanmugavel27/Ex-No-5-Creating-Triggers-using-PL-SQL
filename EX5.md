# Ex. No: 5 Creating Triggers using PL/SQL

### AIM: To create a Trigger using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create salary_log table with following attributes (log_id NUMBER GENERATED ALWAYS AS IDENTITY, empid NUMBER,empname VARCHAR(10),old_salary NUMBER,new_salary NUMBER,update_date DATE);
3. Create a trigger named as log_salary-update.
4. Inside the trigger block, Insert the values into the salary_log table whenever the salary is updated.
5. End the trigger.
6. Update the salary of an employee in employee table.
7. Whenever a salary is updated for the employee it must be logged into the salary_log table with old salary and new salary.
8. Display the employee table, salary_log table.

### Create employee table
![image](https://github.com/ganeshshanmugavel27/Ex-No-5-Creating-Triggers-using-PL-SQL/assets/122046208/8a541cda-2cec-4981-a3a7-c4e0dbf627fc)


### Create salary_log table
![image](https://github.com/ganeshshanmugavel27/Ex-No-5-Creating-Triggers-using-PL-SQL/assets/122046208/04b9f8a5-5b5f-4c9c-adb6-aef7932722ee)



### PLSQL Trigger code
set serveroutput on
SQL> CREATE OR REPLACE PROCEDURE emplo_data AS
  2  BEGIN
  3  INSERT INTO emplo(empid,empname,dept,salary)
  4  values(1,'ganesh','IT',10000);
  5  INSERT INTO emplo(empid,empname,dept,salary)
  6  values(2,'sathish','doctor',100001);
  7  INSERT INTO emplo(empid,empname,dept,salary)
  8  values(3,'karthi','manager',200000);
  9  COMMIT;
 10  FOR emplo_rec IN (SELECT * FROM emplo)LOOP
 11  DBMS_OUTPUT.PUT_LINE('EMPLOYEE ID:'||emp_rec.empid||',EMPLOYEE NAME:'|| emp_rec.empname||',DEPARTMENT:'||emp_rec.dept||',SALARY:'||emp_rec.salary);
 12  END LOOP;
 13  END;
 14  /
 
### Output:
![image](https://github.com/ganeshshanmugavel27/Ex-No-5-Creating-Triggers-using-PL-SQL/assets/122046208/b70dc2b9-dcc7-477e-8929-c00f0d63e29e)



### Result:
Thus , the output has been successfully verified.
