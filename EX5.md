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
```set serveroutput on
create or replace trigger log_salary7_update
before update on emp7
for each row
declare
v_old_salary number;
v_new_salary number;
begin
v_old_salary := :OLD.salary;
v_new_salary := :NEW.salary;
if v_old_salary <> v_new_salary then
insert into sala_log1(empid, empname, old_salary, new_salary, update_date)
values(:OLD.empid, : OLD.empname, v_old_salary, v_new_salary, SYSDATE);
end if;
end;
/
```
### Output:
![image](https://github.com/ganeshshanmugavel27/Ex-No-5-Creating-Triggers-using-PL-SQL/assets/122046208/b70dc2b9-dcc7-477e-8929-c00f0d63e29e)



### Result:
Thus , the output has been successfully verified.
