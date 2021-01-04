Table - person<br><br>

Instructions<br>
1. Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color.<br>
  id should be an auto-incrementing id/primary key.<br>
2. Add 5 different people into the person database.<br>
  Remember to not include the person_id because it should auto-increment.<br>
3. List all the people in the person table by height from tallest to shortest.<br>
4. List all the people in the person table by height from shortest to tallest.<br><br>
5. List all the people in the person table by age from oldest to youngest.<br>
6. List all the people in the person table older than age 20.<br>
7. List all the people in the person table that are exactly 18.<br>
8. List all the people in the person table that are less than 20 and older than 30.<br>
9. List all the people in the person table that are not 27 (Use not equals).<br>
10. List all the people in the person table where their favorite color is not red.<br>
11. List all the people in the person table where their favorite color is not red and is not blue.<br>
12. List all the people in the person table where their favorite color is orange or green.<br>
13. List all the people in the person table where their favorite color is orange, green or blue (use IN).<br>
14. List all the people in the person table where their favorite color is yellow or purple (use IN).<br>

SQL Solution<br>
Ans 1. Create Table Person(<br>
	ID int identity(1,1) PRIMARY KEY,<br>
	Fullname varchar(100),<br>
	age int,<br>
	height float,<br>
	city varchar(50),<br>
	fav_color varchar(30)<br>
	)<br>
<br>
Ans 2. Insert into Person values('John Carlos',28,5.4,'Jersey City','Blue'),br>
Insert into Person values('Gary Fernandes',32,5.5,'New York','Black'),<br>
('Jennifer D"souza',30,5.2,'New York','Red'),<br>
('Veronica Bill',28,5.0,'Jersey CIty','Purple'),<br>
('James Watt',35,5.8,'New York','Black')<br>
<br>
Ans 3.Select * from Person
Order By height Desc
<br>
Ans 4.Select * from Person
Order By height Asc
<br>
Ans 5.Select * from Person
Order By age Desc
<br>
Ans 6.Select * from Person
Where age > 20
<br>
Ans 7. Select * from Person
Where age = 18
<br>
Ans 8. Select * from Person
Where age < 20 OR age > 30
<br>
Ans 9. Select * from Person
Where age <> 27
<br>
Ans 10. Select * from Person
Where fav_color <> 'Red'
<br>
Ans 11. Select * from Person
Where fav_color <> 'Red' AND fav_color <> 'Blue'
<br>
Ans 12. Select * from Person
Where fav_color = 'Orange' OR fav_color = 'Green'
<br>
Ans 13. Select * from Person
Where fav_color IN ('Orange','Green','Blue')
<br>
Ans 14. Select * from Person
Where fav_color IN ('Yellow','Purple')

Table - orders<br><br>

Instructions<br>
1. Create a table called orders that records: order_id, person_id, product_name, product_price, quantity.<br>
  Add 5 orders to the orders table.<br>
  Make orders for at least two different people.<br>
2. person_id should be different for different people.<br>
3. Select all the records from the orders table.<br>
4. Calculate the total number of products ordered.<br>
5. Calculate the total order price.<br>
6. Calculate the total order price by a single person_id.<br>
<br>
SQL Solution<br>
Ans 1. Create Table Orders(<br>
order_id int identity(101,1) Primary Key,<br>
person_id int Foreign Key References Person(ID),<br>
product_price decimal,<br>
quantity int<br>
)<br>
Ans 2.Insert into Orders values(1,23.56,5),(5,62.55,4),(2,80.00,6),(5,65,3),(4,100,5),(3,60,2)
<br>
Ans 3. Select * from Orders
<br>
Ans 4. Select SUM(quantity) AS Total_Producs from Orders
<br>
Ans 5. Select SUM(product_price*quantity) AS Total_OrderPrice from Orders
<br>
Ans 6. Select SUM(product_price*quantity) AS Total_OrderPrice from Orders
Where person_id = 5

Table - artist <br><br>

Instructions<br>
1. Add 3 new artists to the artist table. ( It's already created )<br>
2. Select 10 artists in reverse alphabetical order.<br>
3. Select 5 artists in alphabetical order.<br>
4. Select all artists that start with the word 'Black'.<br>
5. Select all artists that contain the word 'Black'.<br>
<br>
SQL Solution<br>
Ans 1. Insert into Artist values(1001,'David Jones','The Day I met you'),(1002,'Haris Black','Love you till the moon & back'),<br>
(1003,'Frank Miller','Sunshine you are my sunshine'),(1004,'Jennifer Gomes','Everything is Best'),<br>
(1005,'Jack Black','Forever and Forever')<br>
Ans 2. Select * from Artist<br>
Order by Name Desc<br>
Limit 5<br>
Ans 3. Select * from Artist<br>
 Order by Name Asc<br>
Limit 5<br>
Ans 4. Select * from Artist<br>
Where Name LIKE 'Black%'<br>
Ans 5. Select * from Artist<br>
Where Name LIKE '%Black%'
<br>

Table - employee<br><br>

Instructions<br>
1. List all employee first and last names only that live in Jersey City.<br>
2. Find the birthdate for the youngest employee.<br>
3. Find the birthdate for the oldest employee.<br>
4. Find everyone that reports to Max Hopkins (Use the ReportsTo column).<br>
  You will need to query the employee table to find the Id for Nancy Edwards<br>
5. Count how many people live in Jersey CIty.<br>

SQL Solution <br>
Ans 1.Select FirstName,LastName from employee
Where city = 'Jersey City'
<br>
Ans 2.Select MAX(birth_date) AS Youngest_Employee from Employee
<br>
Ans 3.Select MIN(birth_date) AS Oldest_Employee from Employee
<br>
Ans 4.Select * from Employee<br>
Where reporting = 'Max Hopkin'
<br>
Ans 5. Select COUNT(employee_id) AS Total_Count from Employee
Where city = 'Jersey City'
<br>

Table - invoice <br><br>

Instructions<br>
1. Count how many orders were made from the USA.<br>
2. Find the largest order total amount.<br>
3. Find the smallest order total amount.<br>
4. Find all orders bigger than $5.<br>
5. Count how many orders were smaller than $5.<br>
6. Count how many orders were in CA, TX, or AZ (use IN).<br>
7. Get the average total of the orders.<br>
8. Get the total sum of the orders.<br>

SQL Solution
Ans 1. Select * from invoice
Where billing_country = 'USA'
<br>
Ans 2. Select MAX(total) AS Largest_Total from invoice
<br>
Ans 3. Select MIN(total) AS Smallest_Total from invoice<br>
Ans 4. Select * from invoice
Where total > 50
<br>
Ans 5. Select COUNT(*) AS 'No. of Orders' from invoice
Where total > 100
<br>
Ans 6. Select COUNT(*) AS 'OrderByCountry' from invoice
Where billing_country IN  ('USA','CA','TX')
<br> 
Ans 7. Select AVG(total) AS AvgTotal from invoice 
<br>
Ans 8. Select SUM(total) AS SumofTotal from invoice













