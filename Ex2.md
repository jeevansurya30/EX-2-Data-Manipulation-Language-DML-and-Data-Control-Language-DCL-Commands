DATE: 11/08/23
# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/184edb77-e86b-4823-a494-dbc9516a0e18)


### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```
delete from manager where salary<2750;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/0b9f9657-0f4c-4185-821a-a152fc9f5608)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/561b67bd-63fd-43fa-9b30-eda165bfec69)

### Q5)	List the names of Clerks from emp table.
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/4e91c9d8-4cac-4e0a-9e10-a274c3ca8353)


### QUERY:
```
select ename from manager where designation='clerk';
```


### OUTPUT:



### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/a3e8b2e1-0926-4a81-96c4-94eb9b7f862e)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/9af6f6e5-cf6d-4487-a3a8-f165efa5f8d2)



### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/f5b1496b-3523-49d1-841c-e93936614685)



### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/608ef772-d24a-4a50-a0d3-8c4e858a2b20)



### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/ea0f9c2a-e4c1-4380-a6cc-18fb93dbece8)




### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/17e42721-ee67-4284-a667-37e4e897679e)



### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/11cc0780-7961-4cdd-816d-c283cde11a44)


### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/c197fe99-8383-4e40-b65e-a4ad42a9b5ee)



### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select max(salary) from manager;
select min(salary) from manager;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/5828f128-9e25-4d2c-a23e-a3cd276bf2a3)



### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/jeevansurya30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/129417865/37f5c8e0-1dc6-442f-a28e-8dfd7660cdbe)
