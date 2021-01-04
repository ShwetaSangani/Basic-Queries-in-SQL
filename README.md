In this project we are creating,inserting and querying data using SQL.
Also includes Joins, Nested queries, updating rows, group by and distinct.

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
<br>

JOINS<br><br>

1. Get all invoices where the unit_price on the invoice_line is greater than $0.99.<br>
2. Get the invoice_date, customer first_name and last_name, and total from all invoices.<br>
3. Get the customer first_name and last_name and the support rep's first_name and last_name from all customers.<br>
4. Get the album title and the artist name from all albums.<br>
5. Get all playlist_track track_ids where the playlist name is Music.<br>
6. Get all track names for playlist_id 5
7. Get all track names and the playlist name that they're on ( 2 joins 
8. Get all track names and album titles that are the genre Alternative & Punk ( 2 joins ).
9. Get all tracks on the playlist(s) called Music and show their name, genre name, album name, and artist name.
At least 5 joins.
<br><br><br>

SQL Solution <br>
Ans 1. Select * from invoice i<br>
JOIN invoice_line inl ON i.invoice_id = inl.invoice_line_id<br>
Where inl.unit_price > 0.99<br>
Ans 2 . Select inc.invoice_date,c.First_name,c.Last_name,inc.total<br>
from customer c<br>
JOIN invoice inc ON c.customer_id = inc.customer_id<br>
Ans 3. Select c.first_name,c.last_name,e.first_name,e.last_name<br>
from customer c<br>
JOIN employee e ON c.support_rep_id = e.employee_id<br>
Ans 4. Select alb.title,art.name<br>
from album alb<br>
JOIN artist art ON alb.artist_id = art.id<br>
Ans 5. Select pt.track_id<br>
from playlist_track pt<br>
JOIN playlist p ON pt.playlist_id = p.playlist_id<br>
where p.name = 'Music'<br>
Ans 6. Select t.name <br>
from track t<br>
JOIN playlist_track pt ON t.track_id = playlist_track_id<br>
Where playlist_id = 5<br>
Ans 7. Select t.name,p.name
from track t
JOIN playlist_track pt ON t.track_id = pt.track_id
JOIN playlist p ON pt.playlist_id = p.playlist_id
Ans 8. Select t.name,a.title<br>
from track t<br>
JOIN album a ON t.album_id = a.album_id<br>
JOIN genre g ON g.genre_id = t.genre_id<br>
Where g.name = 'Alternative & Punk'<br>
Ans 9. Select t.name from 
track t
JOIN playlist_track pt ON t.track_id = pt.track_id
JOIN playlist p ON p.playlist_id = pt.playlist_id
JOIN genre g ON g.genre_id = t.genre_id
JOIN album a ON a.album_id = t.album_id
JOIN artist at ON at.id = a.album_id
Where p.name = 'Music'
<br><br>

Nested Queries
1. Get all invoices where the unit_price on the invoice_line is greater than $0.99.<br>
2. Get all playlist tracks where the playlist name is Music.<br>
3. Get all track names for playlist_id 5.<br>
4. Get all tracks where the genre is Comedy.<br>
5. Get all tracks where the album is Fireball.<br>
6. Get all tracks for the artist Queen ( 2 nested subqueries ).<br><br>

SQL Solution <br>
Ans 1. Select * from invoice<br>
Where invoice_id IN (Select invoice_id from invoice_line where unit_price > 50)<br>
Ans 2. Select * from playlist_track<br>
Where playlist_id IN (Select playlist_id from playlist where name = 'Music')<br>
Ans 3. Select name from track<br>
Where track_id IN (Select track_id from playlist_track where playlist_id = 5)<br>
Ans 4. Select * from track<br>
where genre_id IN (select genre_id from genre where name = 'Comedy' )<br>
Ans 5. Select * from track<br>
where album_id IN (select album_id from album where title = 'Fireball')<br>
Ans 6. Select * from track<br>
Where album_id IN (<br>
	Select album_id from album where artist_id IN (<br>
		Select artist_id from artist where name = 'Queen'<br>
		)<br>
	)<br>
	
UPDATING ROWS<br><br>

1. Find all customers with fax numbers and set those numbers to null.<br>
2. Find all customers with no company (null) and set their company to "Self".<br>
3. Find the customer Julia Barnett and change her last name to Thompson.<br>
4. Find the customer with this email luisrojas@yahoo.cl and change his support rep to 4.<br>
5. Find all tracks that are the genre Metal and have no composer. Set the composer to "The darkness around us".<br>

SQL Solution <br><br>
Ans 1. Update customer<br>
SET fax = NULL<br>
Where fax IS NOT NULL<br>
Ans 2. Update customer<br>
SET company = 'Self'<br>
Where company IS NULL<br>
Ans 3. Update customer<br>
SET last_name = 'Thompson'<br>
where first_name = 'Julia' AND last_name = 'Barnett'<br>
Ans 4. Update customer<br>
SET support_rep_id = 4<br>
Where email = 'luisrojas@yahoo.cl'<br>
Ans 5. Update track<br>
SET composer = 'The darkness aroubd us'<br>
Where genre_id = (Select genre_id from genre where name = 'Metal')<br>
AND composer IS NULL<br>

GROUP BY<br><br><br>
1. Find a count of how many tracks there are per genre. Display the genre name with the count.<br>
2. Find a count of how many tracks are the "Pop" genre and how many tracks are the "Rock" genre.<br>
3. Find a list of all artists and how many albums they have.
<br>
SQL Solution<br><br>

Ans 1. Select COUNT(*),g.name<br>
From track t<br>
JOIN genre g ON g.genre_id = t.genre_id<br>
Group By g.name<br>
Ans 2. Select COUNT(*),g.name<br>
From track t<br>
JOIN genre g ON g.genre_id = t.genre_id<br>
Group By g.name<br>
Having g.name = 'Pop' AND g.name = 'Rock'<br>
Ans 3. Select SUM(album_id),art.name<br>
from album alb<br>
JOIN artist art ON alb.artist_id = alb.artist_id<br>
Group By art.name<br>

DISTINCT<br><br>

1. From the track table find a unique list of all composers.<br>
2. From the invoice table find a unique list of all billing_postal_codes.<br>
3. From the customer table find a unique list of all companys.<br>


SQL Solution<br><br>
Ans 1. Select DISTINCT first_name,last_name from composers<br>
Ans 2. Select DISTINCT billing_postal_code from invoice<br>
Ans 3. Select DISTINCT company from customer
<br>





















