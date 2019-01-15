1. Using a subquery, find the names of all the tracks for the album "Californication". What is the title of the 8th track?

select Tracks.Name,Albums.Title
from Tracks
left join Albums
on Tracks.AlbumId=Albums.AlbumId
where Albums.Title="Californication";

2. Find the total number of invoices for each customer along with the customer's full name, city and email. After running the query described above, what is the email address of the 5th person, František Wichterlová? Enter the answer below (feel free to copy and paste).

select a.FirstName,a.LastName,a.City,a.Email,count(a.InvoiceId) as TotalNum
from
(select Customers.FirstName,Customers.LastName,Customers.City,
Customers.Email,Invoices.InvoiceId
from Customers
left join Invoices
on Customers.CustomerId=Invoices.CustomerId) as a
group by a.FirstName
having a.FirstName="František";

3. Retrieve the track name, album, artistID, and trackID for all the albums. What is the song title of trackID 12 from the "For Those About to Rock We Salute You" album? Enter the answer below.

select Tracks.Name,Tracks.TrackId,Albums.Title,Albums.ArtistId
from Tracks
left join Albums
on Tracks.AlbumId=Albums.AlbumId
where Albums.Title like "For Those About to Rock We Salute You" 
and Tracks.TrackId=12;

4. Retrieve a list with the managers last name, and the last name of the employees who report to him or her. After running the query described above, who are the reports for the manager named Mitchell (select all that apply)?

select a.LastName as EmployeeLast,a.ReportsTo,b.LastName as ManagerLast
from Employees as a
left join Employees as b
on a.ReportsTo=b.EmployeeId
where b.LastName like "Mitchell"

5. Find the name and ID of the artists who do not have albums. After running the query described above, two of the records returned have the same last name. Enter that name below.

select a.Name,count(a.Name)
from
(select Artists.ArtistId,Artists.Name,Albums.AlbumId
from Artists
left join Albums
on Artists.ArtistId=Albums.ArtistId
where Albums.AlbumId is null) as a
group by a.Name
order by count(a.Name) asc

6. Use a UNION to create a list of all the employee's and customer's first names and last names ordered by the last name in descending order. After running the query described above, determine what is the last name of the 6th record? Enter it below. Remember to order things in descending order to be sure to get the correct answer.

select FirstName, LastName from Employees
union
select FirstName,LastName from Customers
order by LastName desc

7. See if there are any customers who have a different city listed in their billing city versus their customer city.

select Customers.FirstName,Customers.City,Invoices.BillingCity
from Customers
left join Invoices
on Customers.CustomerId=Invoices.CustomerId
where Customers.City<>Invoices.BillingCity
