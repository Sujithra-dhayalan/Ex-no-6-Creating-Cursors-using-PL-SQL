
# Ex. No: 6 Creating Cursors using PL/SQL
## Date:
### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
create table employee((empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
insert into employee values(1,'John','HR',50000);
insert into employee values(2,'joe','IT',60000);
insert into employee values(3,'Bob','Finance',55000);
```

### PLSQL Cursor code
```
set serveroutput on

declare 
cursor employee_cursor is
select empid,empname, dept, salary 
from employee;
emp_id number;
emp_name char(50);
emp_dept char(50);
emp_salary int;
begin 
open employee_cursor;
loop
fetch employee_cursor into emp_id, emp_name, emp_dept, emp_salary;
exit when employee_cursor%NOTFOUND;
dbms_output.put_line('Employee ID: '|| emp_id);
dbms_output.put_line('Employee Name: '|| emp_name);
dbms_output.put_line('Department: '|| emp_dept);
dbms_output.put_line('Salary: '|| emp_salary);
dbms_output.put_line('----------------------');
end loop;
close employee_cursor;
end;
/
```

### Output:

![image](https://github.com/Sujithra-dhayalan/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/115523950/11e1d7b0-eb63-42ad-b491-9890ea4a7e08)


### Result:

Hence a cursor using PL/SQL is created successfully.
